---
status: publish
published: true
title: Gnome3の時計を非表示にする
date: 2011-05-04 08:59:17
categories:
- pc
tags:
- Gnome
- Clock
- diff
---
ど真ん中に時刻が表示されて気になるので非表示にしました。
<blockquote>--- /usr/share/gnome-shell/js/ui/panel.js 2011-05-03 14:50:55.169821856 +0900
+++ /usr/share/gnome-shell/js/ui/panel.js_ 2011-05-03 14:55:52.213983414 +0900
@@ -18,7 +18,7 @@
const PopupMenu = imports.ui.popupMenu;
const PanelMenu = imports.ui.panelMenu;
const StatusMenu = imports.ui.statusMenu;
-//const DateMenu = imports.ui.dateMenu;
+const DateMenu = imports.ui.dateMenu;
const Main = imports.ui.main;
const Tweener = imports.ui.tweener;

@@ -938,9 +938,9 @@
this._menus.addMenu(appMenuButton.menu);

/* center */
- //this._dateMenu = new DateMenu.DateMenuButton();
- //this._centerBox.add(this._dateMenu.actor, { y_fill: true });
- //this._menus.addMenu(this._dateMenu.menu);
+ this._dateMenu = new DateMenu.DateMenuButton();
+ this._centerBox.add(this._dateMenu.actor, { y_fill: true });
+ this._menus.addMenu(this._dateMenu.menu);

/* right */</blockquote>
