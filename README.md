# Ion Tray

A Web Component which enables you to have central content with a left and right tray which can 'push' into view.

## Usage

	<ion-tray class="my-tray">
		<section class="tray-left" data-width="260px">
			Left tray content
		</section>
		<section class="tray-center">
			Right tray content
		</section>
		<section class="tray-right" data-width="50%">
			Right tray content
		</section>
	</ion-tray>
	
Elements do not have to be sections, the required part is the `tray-left`, `tray-center`, `tray-right`  class names.

`data-width` only applies to the left and right trays and will default to `100%` if you do not specify it.

## Opening trays

Ion components are stateless and interaction is achieved through events. The component listens for the following events on the `<ion-tray>` element:

**showLeftTray** Shows the left tray.

**showCenterTray** Shows the center tray.

**showRightTray** Shows the right tray.

For example:

	var ionTray = document.querySelector('.my-tray');
	ionTray.dispatchEvent(new Event('showLeftTray'));

**Note that when you open a side tray the user can click anywhere in the center tray to bring it back into position.**

## Styling the trays

The styling of the content is up to you. To style the tray containers you need to use the `::shadow` pseudo-selector.

	.my-tray::shadow .tray-left {
		background-color: black;
		color: white;
	}
	.my-tray::shadow .tray-center {
		background-color: lightgrey;
	}
	.my-tray::shadow .tray-right {
		background-color: purple;
		color: white;
	}
	
You can also apply styles based on a side tray being open:

	.my-tray::shadow .side-tray-visible .tray-center {
		background-color: red;
	}
	
