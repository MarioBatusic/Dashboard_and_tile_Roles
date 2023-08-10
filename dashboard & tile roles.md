# `dashboard` Role

## Introduction

The dashboard is a container that is being used more and more.

A dashboard is a graphical representation of information, data, or performance indicators presented in a compact form on a single screen. It provides a concise and easy-to-understand overview of various aspects of a business process, website, application or other system. Dashbboards also often serve as an entry-point to the individual areas of a web application.

In terms of layout, dashboards either take up an entire application window, or only the main area on the right side or even just part of the application window. Since there is no semantic markup for the dashboard area up to now, it is very difficult, especially for the screen reader users and for the users of the magnifier software, to determine that some part of the page contents is is a dashboard and where are its beginning and its end.

In addition, dashboards are areas that Matt King describes in his proposal [An Accessibility Opportunity Hidden in Modeless Web Dialogs](https://gist.github.com/mcking65/11882ebbe2889964c62ab5a16ab528c3) as

> similar to modeless dialogs.

Fabasoft Cloud uses e.g. a dashboard as its Home:
![Fabasoft Cloud Home](HomeDashboard.png)

or as the access point to a web app on the Fabasoft Cloud Platform:
![Cloud Organization Dashboard](CloudOrganizationDashboard.png)

## ARIA Semantics

- Role name: `dashboard`
- Derived from the role: `dialog` 
- `aria-modal=false` (default)
- `aria-orientation=both` (default)
- Allowed Accessibility Children:
   - `heading`
   - `tile`

# Role `tile`

## Description

The `tile` role is the accessibility child of the `dashboard` role. The elements with this role are similar to the elements with the `cell` role in that they are placed next to each other in a table cell-like manner, both horizontally and vertically. Like table cells they can be of different sizes. The tiles thus behave like `td` elements that have different values for their `colspan` and/or `rowspan` attributes. This comparisson is only intended to help to better understand the concept and does not mean that the tiles in the markup always follow the table paradigm.

## ARIA Semantics
- Role name: `tile` or `card`
- Similar concept: table cell (`cell` element)
- Accessibility Parent: `dashboard`

# Keyboard Shortcuts

This digression belongs more to the ARIA Authoring Practices Guide, but it is useful to think about keyboard shortcuts concerning a new role right away.

Some of the dashboards available on the Web allow navigation between the tiles using the arrow keys or the tab key. Very few allow resizing and repositioning using the keyboard. However, most dashboards do not provide for their own keyboard navigation between the tiles.

All functionalities that are possible with the mouse must also be available with the keyboard:

- Navigation between the individual tiles
- Changing the tile order
- Customizing the tile size.

Here are some suggested keyboard shortcuts:

| Keyboard Shortcut | Function |
|------------------|--------------------|
| F6 / Shift+F6 | Leave the Dashboard |
| arrow keys | Navigate between the tiles (in visual order). The focus is always set to the first widget in a tile. |
| Ctrl+right arrow | Go to the next tile in the complete tile order |
| Ctrl+Left Arrow | Go to the previous tile in the complete tile order |
| Tab and Shift+Tab | Go to next/previous widget (through all tiles) |

All functionalities of an individual  tile that are possible with the mouse must also be made available via keyboard. To adjust the size and/or the position of a tile in the dashboard using the keyboard, there are two alternative possibilities:

1. A menu button in the tile opens a menu with corresponding options, or
2. Shift+F10 / context menu key opens a context menu with appropriate options when the focus is on a widget in a tile.
