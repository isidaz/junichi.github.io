---
status: publish
published: true
title: C#でRSSIとESSIDとBSSIDを取得する
date: 2010-12-29 02:47:39
categories:
- Programing
tags:
- C#
- CSharp
- WiFi
- RSSI
- ESSID
- BSSID
- Programing
---
<a href="http://managedwifi.codeplex.com/">Managed Wifi API</a>

上記はWindows XP SP2以降のNative WiFi APIをC#で利用するためのライブラリ。これを利用した。

繁盛にAPIを叩くと例外が発生してしまう様。解決策はないだろうか。1秒間隔でも起きてしまう。
<pre>using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using NativeWifi;

namespace ConsoleApplication1
{
  class Program
  {
    static void Main(string[] args)
    {
      Program p = new Program();

      while (true)
      {
        p.GetRssi();
        System.Threading.Thread.Sleep(1000);
      }
    }

    private void GetRssi()
    {
      WlanClient client = new WlanClient();
      StringBuilder sb = new StringBuilder();

      foreach (WlanClient.WlanInterface wlanIface in client.Interfaces)
      {
        Wlan.WlanBssEntry[] wlanBssEntries = wlanIface.GetNetworkBssList();

        foreach (Wlan.WlanBssEntry wlanBssEntry in wlanBssEntries)
        {
          byte[] macAddr = wlanBssEntry.dot11Bssid;
          byte[] ssid = wlanBssEntry.dot11Ssid.SSID;

          sb.Append(BitConverter.ToString(macAddr) + ",");
          sb.Append(Encoding.ASCII.GetString(ssid) + ",");
          sb.Append(wlanBssEntry.rssi.ToString());
          sb.AppendLine();
        }
      }

      Console.Write(sb.ToString());

    }

  }
}
</pre>
