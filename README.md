ScrollableItemList
====================

### Description

An Android RecyclerView List with items that can scroll to reveal more content on the side. This view has been inspired by the one found in the Reddit News App.

### Demo

[![Gif Demo](http://i.imgur.com/9NPgfsN.gif)]

### Notes on using this

The view has been created using standard views now available with Android Lollipop and its compatibility libraries. The list is a `RecyclerView` with a `LinearLayoutManager`. Each item in the list is essentially a ViewPager with two views; a `CardView` and `FrameLayout` with three buttons.

Everything else can be used normally except the ``RecyclerViewAdapter.java`` where most of the work is required.

The challenges were as follows:

**1)** The ViewPager does not inflate properly inside the RecyclerView.

In order to solve this, the width of the ViewPager was manually set to the current width of the screen when it inflates inside the adapter. The height should be specified manaully and `wrap_content` attribute cannot be used.

**2)** The ViewPagers do not retain state as the list items are scrolled away from current view and back.

In order to solve this problem, the `RecyclerViewAdapter` holds a list of states for each of the ViewPager and sets them back when a previously modified item comes back in view.

### License
```
The MIT License (MIT)

Copyright (c) 2014 Oleksandr Melnykov

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
