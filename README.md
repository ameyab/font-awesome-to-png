Font Awesome to PNG
===================

This program allows you to extract the awesome
[Font Awesome] (http://fortawesome.github.com/Font-Awesome/) icons as PNG images
of specified size.

### Usage

    font-awesome-to-png.py [-h] [--color COLOR] [--filename FILENAME]
                           [--font FONT] [--css CSS] [--list] [--size SIZE]
                           icon [icon ...]

    positional arguments:
      icon                 The name(s) of the icon(s) to export (or "ALL" for
                           all icons)

    optional arguments:
      --color COLOR        Color (HTML color code or name, default: black)
      --filename FILENAME  The name of the output file (it must end with
                           ".png"). If all files are exported, it is used as a
                           prefix.
      --font FONT          Font file to use (default: fontawesome-webfont.ttf)
      --css CSS            Path to the CSS file defining icon names (instead of
                           the predefined list)
      --list               List available icon names and exit
      --size SIZE          Icon size in pixels (default: 16)

    hidden optional arguments:
     --list-update         List available icon names and codes in format suitable
                           for updating the program source.

To use the program, you need the Font Awesome TTF file, which is available in
[Font Awesome Github repository] (https://github.com/FortAwesome/Font-Awesome).

The internal icon list is matched to Font Awesome 4.1.0.  To use a later/different
version, use font-awesome.css from the Font Awesome GitHub repository.

### Examples

Export the "play" and "stop" icons as 24x24 pixels images:

    font-awesome-to-png.py --size 24 play stop

Export the asterisk icon as 32x32 pixels image, in blue:

    font-awesome-to-png.py --size 32 --color blue asterisk

Export all icons as 16x16 pixels images:

    font-awesome-to-png.py ALL

### Dependecies 
This program depends on the Python Imaging Library (PIL). Please install the Pillow, the ‘friendly’ PIL fork by Alex Clark and Contributors (http://pillow.readthedocs.org/en/latest/index.html).

__Mac OS X users__: Please note that the Apple LLVM compiler in Xcode 5.1 treats unrecognized command-line options as errors. This may cause an “clang: error: unknown argument” exception when building Pillow on Mac OS X 10.9x. 

A workaround is to downgrade the  ARCHFLAGS environment variable to downgrade the error to a warning. 

You can install Pillow using the following command should you run into the "clang: error: unknown argument" exception.

    sudo ARCHFLAGS=-Wno-error=unused-command-line-argument-hard-error-in-future pip install mitmproxy
    
__Reference__: [http://bruteforce.gr/bypassing-clang-error-unknown-argument.html] (http://bruteforce.gr/bypassing-clang-error-unknown-argument.html)


