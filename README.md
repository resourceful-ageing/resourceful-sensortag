# resourceful-sensortag

## Flashing
New sensortag CC2650STK's can be flash using the SmartRF Flash Programmer 2 software from TI.
Connect you Sensortag using the Debugger and in the Main tab select Multiple flash images which can be found in the directory "hex".

When flashing the sensortag for the first time, make sure to include `bim_extflash.hex`.

## Changing the firmware
Download/install the BLE-stack (2.2.1) from TI website (http://www.ti.com/tool/ble-stack)
You should get a directory like "ti\simplelink\ble_sdk_2_02_01_18\src\examples\sensortag\cc26xx\app"
Check the file differences with the files provided in the "src\app" directory.

Install Code Composer Studio v7 (CCS) and load the following projects:
- \ti\simplelink\ble_sdk_2_02_01_18\examples\cc2650stk\sensortag\ccs\app
- \ti\simplelink\ble_sdk_2_02_01_18\examples\cc2650stk\sensortag\ccs\stack

### Configure CCS

**Configure correct compiler**
Help -> Install new software:
 - Disable "Show only latest versions of available software"
 - Install: Work with -> TI Compiler Updates -> ARM Compiler Tools 5.2.6
 - File -> Properties -> General -> Compiler version (confirm it's TI v5.2.6)

**Build Hex files**
File -> Properties -> Build -> ARM Hex Utility:
 - Enable ARM Hex Utility
 - Add "--ti_txt" via "Edit Flags..."

For developing a new firmware, click the "Debug" tool (bug icon).
For creating a new hex-file, click the "Build" tool (hammer icon).

Debugging automatically loads the firmware onto the connected sensortag.

More details can be found on http://www.ti.com/lit/ug/swru393d/swru393d.pdf
