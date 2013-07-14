MonodroidT4Templates
====================

A bunch of T4 templates to make your mono for android coding less mandrolic.

The AutoTT.conif file can be used with https://github.com/MartinF/Dynamo.AutoTT to automatically execute your t4 templates when resources change.
================================================================================
LayoutToView.tt - Simplified Layout Access
================================================================================

Simply copy the LayoutToView.tt to a folder called Views in the root of your project. It will automatically generates a c# view class which you can use to access all the android layouts (that have ids). This allows you to easily mix hand coded layouts with axml.  
Creating a class to access you layout in code is as simple as :

// Get get an accessor for an existing view 
var grid = new ImageGrid(Window.DecorView.FindViewById(Resource.Id.ImageGridRoot));

// or to create a new view 
var imageDetailLaout = new ImageDetailLayout(context);

================================================================================
PrefsToSettings.tt - Simplified Preferences Access
================================================================================

Simply copy the PrefsToSettings.tt file to a folder called Settings in the root of your project. It will automatically generate C# accessors for your preferences.xml.

To create a preferences object simply use :

var preferences = new Preferences(context);

and away you go.

================================================================================
GenerateDrawables.tt - Use your assets folder to automatically generate all your dpi dependant bitmaps.
================================================================================

Simply copy this file into your Assets folder and then rename your assets according to the following format <basename>_dpWWxHH.<ext> (e.g. navigate_up_dp32x32.png). High resolution assets will be automatically scaled to the correct size for the standard dpi targets and the dpi target folders will be generated (drawable-hdpi, drawable-ldpi...)

For example, if you have a nice 512x512 button image, and on screen it will be 48x48, name the file nice_image_dp48x48.png. GenerateDrawables.tt will generate the ldpi:36x36, mdpi:48x48, hdpi:72x72, xhdpi:96x69, images in the 'nice_image.png' files in the correct directories.



