# DOS

DOS emulator in JavaScript.

## Web:

https://lrusso.github.io/DOS/DOS.htm

## How to enable/disable the sound:

- On Mac you must press ```Command U```.
- On Windows/Linux you must press ```Ctrl U```.
 
## How to download the disk image:

- On Mac you must press ```Command I```.
- On Windows/Linux you must press ```Ctrl I```.

## How to use a different the disk image:

Update the ```DISK_DATA``` variable located in the ```DISK.js``` file with your new JSON.

## How to delete the disk image from cache:

- Browse to https://lrusso.github.io/DOS/DOS.htm?clearcache

## How to convert a IMG disk file to a JSON file:

- Browse to https://lrusso.github.io/DOS/imgConverter.htm
- Select your IMG disk file.
- A JSON file will be automatically generated and downloaded.

## Differences with the original project:

- Fixed issue when handling JSON5 files.
- Added a logic for enabling/disabling the sound.
- Fixed issue when panning is enabled in EGA mode.
- Fixed issue when locking the pointer several times.
- Removed a logic that was using REST for getting the resources.
- Easier approach for using a disk, just update the ```DISK_DATA``` variable.

## Based on the work of:

https://github.com/jeffpar/pcjs
