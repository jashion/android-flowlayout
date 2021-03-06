# Android flow layout

## Introduction

Extended linear layout that wrap its content when there is no place in the current line.

## Demonstration

Orientation: HORIZONTAL, Gravity: FILL, LayoutDirection: LTR

![](https://github.com/ApmeM/android-flowlayout/raw/master/img/LANDSCAPE_LTR_FILL_HORIZONTAL_DEBUG.png)
![](https://github.com/ApmeM/android-flowlayout/raw/master/img/PORTRAIT_LTR_FILL_HORIZONTAL_DEBUG.png)

Orientation: HORIZONTAL, Gravity: RIGHT & BOTTOM, LayoutDirection: RTL

![](https://github.com/ApmeM/android-flowlayout/raw/master/img/LANDSCAPE_RTL_RIGHTBOTTOM_HORIZONTAL_DEBUG.png)
![](https://github.com/ApmeM/android-flowlayout/raw/master/img/PORTRAIT_RTL_RIGHTBOTTOM_HORIZONTAL_DEBUG.png)

Orientation: VERTICAL, Gravity: CENTER, LayoutDirection: LTR

![](https://github.com/ApmeM/android-flowlayout/raw/master/img/LANDSCAPE_LTR_CENTER_VERTICAL_DEBUG.png)
![](https://github.com/ApmeM/android-flowlayout/raw/master/img/PORTRAIT_LTR_CENTER_VERTICAL_DEBUG.png)

Debug is switched off:

![](https://github.com/ApmeM/android-flowlayout/raw/master/img/LANDSCAPE_LTR_FILL_HORIZONTAL_NODEBUG.png)
![](https://github.com/ApmeM/android-flowlayout/raw/master/img/PORTRAIT_LTR_FILL_HORIZONTAL_NODEBUG.png)

## Installation and usage

Take from maven repository (<http://search.maven.org/#search%7Cga%7C1%7Corg.apmem.tools>, <http://mvnrepository.com/search.html?query=org.apmem.tools>) or add FlowLayout and other components to your solution

Add it as dependency in Gradle as:

	compile 'org.apmem.tools:layouts:1.6@aar'

Or maven

        <dependency>
            <groupId>org.apmem.tools</groupId>
            <artifactId>layouts</artifactId>
            <version>1.4</version>
            <scope>provided</scope>
        </dependency>

Add the following xml code into your layout/something.xml:

	<org.apmem.tools.layouts.FlowLayout
		xmlns:android="http://schemas.android.com/apk/res/android"
		android:layout_width="fill_parent"
		android:layout_height="wrap_content"
	>
	</org.apmem.tools.layouts.FlowLayout>

To change default horizontal and vertical spacing between elements in layout use the following code:
        
	xmlns:f="http://schemas.android.com/apk/res/your.namespace"
	f:horizontalSpacing="6dip"
	f:verticalSpacing="12dip"

To change default direction use the following code

	f:orientation="vertical"

To change layout direction use the following code

	f:layoutDirection="rtl"
	
Android gravity now supported (in combination with elements weight):

        f:weightDefault="1.0"
        android:gravity="fill"

To override default spacing use the following LayoutParameter in the child View element:

	f:layout_horizontalSpacing="32dip"
	f:layout_verticalSpacing="32dip"

Also if you need to break line before some object even if there is enough space for it in the previous line - use the following LayoutParameter in the child view element:

	f:layout_newLine="true"

## Detailed parameters

Layout parameters:

	* horizontalSpacing - default horizontal spacing between elements

	* verticalSpacing - default vertical spacing between elements

	* debugDraw - draw debug information

	* orientation - line direction. Use one of the following values:

		* horizontal - line will be in horizontal direction, linebreak will create new line

		* vertical - line will be in vertical direction, linebreak will create new column

        * android:gravity - standart android gravity supported

        * weightDefault - default weight value for child elements. Used to fill line in case of Gravity.FILL_HORIZONTAL | Gravity.FILL_VERTICAL

        * weightSum - total weight of all elements (used to calculate weight of a specified element)

        * layoutDirection - direction of inner child elements:

                *  ltr - left to right direction

                *  rtl - right to left direction

Child layout parameters:

	* layout_horizontalSpacing - override default horizontal spacing

	* layout_verticalSpacing - override default vertical spacing

	* layout_newLine - brake line before current element even if there is enough place in the current line.

	* android:layout_gravity - standart aandroid gravity supported

        * layout_weight - weight of the element. If not specified "layout.defaultWight" is used.

## Copyrights

   Copyright 2011, Artem Votincev (apmem.org)
 
   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
