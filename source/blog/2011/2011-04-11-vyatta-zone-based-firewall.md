---
layout: post
status: publish
published: true
title: Vyatta Zone-Based Firewallを設定した。
date: 2011-04-11 20:52:46
categories:
- network
---
設定はマニュアルのコピペ。Linuxベースなので、scp等そのまま使えてラッキーだったりする。
<pre>scp /opt/vyatta/etc/config/config.boot jun@192.168.0.1:~/config.boot</pre>
<pre>name private_to_dmz {
  default-action drop
    description "filter traffic from PRIVATE zone to DMZ zone"
    rule 1 {
      action accept
        destination {
          port http,https,ssh,3389
        }
      protocol tcp
    }
  rule 2 {
    action accept
      icmp {
        type-name any
      }
    protocol icmp
  }
}
name public_to_dmz {
  default-action drop
    description "filter traffic from PUBLIC zone to DMZ zone"
    rule 1 {
      action accept
        destination {
          port http,https,ssh
        }
      protocol tcp
    }
  rule 2 {
    action accept
      icmp {
        type-name any
      }
    protocol icmp
  }
  rule 3 {
    action accept
      destination {
        port 53
      }
    protocol udp
  }
}
name to_private {
  default-action drop
    description "filter traffic to PRIVATE zone"
    rule 1 {
      action accept
        protocol all
        state {
          established enable
            related enable
        }
    }
}
name to_public {
  default-action drop
    description "allow all traffic to PUBLIC zone"
    rule 1 {
      action accept
    }
}
receive-redirects disable
send-redirects enable
source-validation disable
syn-cookies enable
}
zone-policy {
  zone dmz {
    default-action drop
      description "DMZ ZONE"
      from private {
        firewall {
          name private_to_dmz
        }
      }
    from public {
      firewall {
        name public_to_dmz
      }
    }
    interface eth1
  }
  zone private {
    default-action drop
      description "PRIVATE ZONE"
      from dmz {
        firewall {
          name to_private
        }
      }
    from public {
      firewall {
        name to_private
      }
    }
    interface eth0
  }
  zone public {
    default-action drop
      description "PUBLIC ZONE"
      from dmz {
        firewall {
          name to_public
        }
      }
    from private {
      firewall {
        name to_public
      }
    }
    interface eth2
  }
}</pre>
