Animation exercise remember-me
===================

This is an implementation of an animation exercise for a remember me dialog box. The original inspiration was taken from a  ([medium.com article](https://medium.com/bridge-collection/improve-the-payment-experience-with-animations-3d1b0a9b810e).

![alt text](https://raw.githubusercontent.com/lassehav-oamk/animation-remember-me/master/remember_me.gif)


----------


Main points
-------------

Main points in the implementation are the following:

> **Note:**

> - StackEdit is accessible offline after the application has been loaded for the first time.
> - Your local documents are not shared between different browsers or computers.
> - Clearing your browser's data may **delete all your local documents!** Make sure your documents are synchronized with **Google Drive** or **Dropbox** (check out the [<i class="icon-refresh"></i> Synchronization](#synchronization) section).

#### Perspective
CSS definition controls the 3D rendering needed for a flip effect. The value itself defines how many pixels a 3D element is placed from the view.
    perspective: 600px;

Important to notice is that the perspective CSS definition needs to be used by the parent of the actual element doing the flip effect.

#### Transform

The actual flip effect is achived by toggling the rotateX value of the transform property.
The transform-origin defines the 'hinge' eg. the origin point for the flip.

    .collapse
    {
	    ...
	    transform: rotateX(-90deg);
	    transform-origin: 0px 0px;
	}
	.collapse-visible
	{
		...
		transform: rotateX(0deg);
	}

#### Custom transition timing function
A custom transition timing function is used to achieve the followthrough / overshoot animation effect.

    transition-timing-function: cubic-bezier(0.730, 0.005, 0.265, 1.550);
