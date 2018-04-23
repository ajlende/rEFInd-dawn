# Dawn rEFInd Theme

Theme for the [rEFInd](http://www.rodsbooks.com/refind/) UEFI boot manager.

Screenshots coming soon... Or whenever I can figure out why F10 isn't working to take the screenshot. For now, look at the icons and imagine what it would look like with them on this background.

![Background Image](banner.png)

### Installation

 1. Locate your refind EFI directory. This is commonly `/boot/EFI/refind` though it will depend on where you mount your ESP and where rEFInd is installed. `fdisk -l` and `mount` may help.

 2. Create a folder called `themes` inside it, if it doesn't already exist

 3. Clone this repository into the `themes` directory.

 4. To enable the theme add `include themes/rEFInd-dawn/theme.conf` at the end of `refind.conf`.

Here's an example menuentry configuration that I use.

```nginx
menuentry "Windows 10" {
    icon \EFI\refind\themes\rEFInd-dawn\icons\os_win.png
    loader \EFI\Microsoft\Boot\bootmgfw.efi
}

menuentry "Arch Linux" {
    icon /EFI/refind/themes/rEFInd-dawn/icons/os_arch.png
    loader vmlinuz-linux
    initrd initramfs-linux.img
    options "root=UUID=XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX rootfstype=ext4 rw quiet splash"
}

menuentry "Netboot XYZ" {
    icon /EFI/refind/themes/rEFInd-dawn/icons/os_network.png
    loader /EFI/netboot/netboot.xyz.efi
}

```

Entries that are autodetected should also show the proper icons if the icon is present. If it isn't showing the proper icons, feel free to open a [pull request](https://github.com/ajlende/rEFInd-dawn/pulls) or an [issue](https://github.com/ajlende/rEFInd-dawn/issues/new) and I can probably make it happen.

## Attribution

### Background

[Camping On Baker](http://www.dylanfurstphoto.com/portfolio-1/a2jipzd42a612qhekydlteyjjuwju0) by [Dylan Furst](http://www.dylanfurstphoto.com)

Slightly Photoshopped by myself.


### Icons

[Flaticons](http://flaticons.net)

You can swap out any of the icons with ones from the Flaticons icon set and they'll feel like they fit right in. The settings used for customizing were `128px` with `16px` padding for the `func_` and `vol_` icons. `vol_` icons background was `#111`. And the `os_` icons were `256px` with `32px` padding.

### Font

[Alma Mono](http://almamono.com) by [Daniel Feldt](http://feldt.nu/)

I wasn't having much luck turning the font into a bitmap font to use for everything else which is why it's text-free.
