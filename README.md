This README file contains information on the contents of the meta-rz-splash layer.

The meta-rz-splash layer replaces the default Yocto logo in the boot splash screen with a Renesas logo.
This has been currently tested on the RZ/G2L SoC with the VLP 4.0.1 (scarthgap). For other VLP version, please check the tags and corresponding README for instructions.

Please see the corresponding sections below for details.

Table of Contents
=================

  I. Adding the meta-rz-splash layer to your build.

 II. Modifying the image.

III. Verifying the splash screen changed.


I. Adding the meta-rz-splash layer to your build
=================================================

Run 'bitbake-layers add-layer meta-rz-splash'


II. Building the image.
=================================================

In build/conf/local.conf, add the following lines to enable to boot splash screen:

        DISTRO_FEATURES:append = " splash"
        IMAGE_INSTALL:append = " psplash"

Next, build your customized image:
	$bitbake core-image-weston


III. Verification
=================================================

On booting the EVK with the modified image, the boot splash screen should now show the Renesas logo.
