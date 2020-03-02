# MSI_GS65_1402_HACKINTOSH_GUIDE
Hi there! I just successfully install the macOS Catalina on my GS65-1402 following [ErrorErrorError's guide](https://github.com/ErrorErrorError/msi-gs65-gs75-hackintosh). That guide is well documentated. Many many thanks to ErrorErrorError. However, the latest model of GS65 has some slight different hardware than the previous generation. I will make a guide about how to install macOS specificlly on my exact model.


## Bluetooth working for Mac Catalina
First of all, I bought a Dw1830 and replace it with the original killer wifi card. I made my bluetooth work in 10.15.3! Thanks to this [thread](https://www.tonymacx86.com/threads/dw1560-bluetooth-on-catalina-10-15-1.286412/page-3). You basically need these three kexts:


BrcmPatch3.kext, BrcmFirmwareData.kext and BrcmBluetoothInjector.kext


Put them in EFI/CLOVER/kexts/Other with Inject Kexts=Yes.
Don't forget to change the Inject parameter in your config.plist! It's detect by default, change it to Yes.


## To do: wifi speed fix
After you put brcm*.kext, you need a bootflag to unlock the full speed of your wifi card:
```
brcmfx-country=US
```
This flag uses the AirportBrcmFixup.kext to fix the 5Ghz channel working frequency issue.
