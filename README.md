# EZ-Tools-GUI
Making KAPE forensic artifact processing easier

<p align="center">
<img src="/screenshot/EZTGui_screenshot.png">
</p>

## TL;DR ##
This is just an interface for Eric Zimmerman forensics tools. Rather than TYPE TYPE SMACK keyboard, by using this tool, just CLICK CLICK PRESS mouse and DONE! 😊

## Introduction ##
EZ Tools GUI - Making KAPE forensic artifact processing easier within several clicks. **Typically, we using KAPE as artifacts collector and Eric Zimmerman (EZ) tools to process the artifact**; which most of his tools are by cmd. Sometimes this can be troublesome; especially when we need to manually type in the command and parameters required altogether. By using this tool, within couple of checkboxes & click, it’s Done!

<img width="80%" height="80%" src="/screenshot/gkape_screenshot.png">

This tool is not any different/advance than KAPE itself; since KAPE also can be used to process its own collected data via KAPE GUI (gkape.exe). But, if you aren't familiar with KAPE GUI, it can take some times to search and ensure the correct module to be use to process artifact that we want.

## Build Status ##
![build](https://img.shields.io/badge/build-passing-green) ![release](https://img.shields.io/badge/release-1.3-blue) ![ps](https://img.shields.io/badge/ps%20(wpf)-v5-blue)

**Currently on version 1.3**

This tool was built based on **PowerShell & WPF** (Windows Presentation Foundation); Microsoft's latest approach to a GUI framework, used with the .NET framework.

Currently it's on working/passing state; the loop logic implemented is a bit out-of-norm. I'll rework that if I got ideas for it. In future, this can be expanded to process others artifact.
 
## Dependencies ##
Its currently using **Eric Zimmerman tools** to process necessary artifact. Tools listed as below:
1. AmcacheParser.exe
2. AppCompatCacheParser.exe
3. BrowsingHistoryView.exe
4. EvtxECmd.exe
5. hindsight.exe
6. JLECmd.exe
7. MFTECmd.exe
8. PECmd.exe
9. SBECmd.exe
10. SrumECmd.exe
11. WxTCmd.exe

This list may expand in future if new there is new important artifact that need to processed in future e.g., processing registry.
 
## How To Use ##
1. Extract forensic artifact that has been collected from target host.
   - It is highly recommended to use **KAPE** as artifact collector.
2. Extract the EZTGui.zip. Run the tool from extracted folder. 
3. Select artifact path e.g., ***C:\artifact_folder\Hostname\C\\***
   - Ensure the selected path is up until ***\C\\*** only e.g., ***I:\kape_output\DESKTOP-J38IE81\2022-02-20T140154_DESKTOP-J38IE81\C\\***
   - <img src="/screenshot/EZTGui_screenshot1.png">
4. Select output path. You may need to created new folder to store the outputs.
5. Select which process/action need to be performed e.g., to process MFT, Prefetch, user browsing history. You can also select multiple action at once.
   - <img src="/screenshot/EZTGui_screenshot2.png">
   - **Reminder: Please do not untick the Loop Bypass action. Or else, your host will crash. Don’t say I didn’t warn you.**
6. Click **Process!** to start the artifact processing. Wait until it finished.
   - <img src="/screenshot/EZTGui_screenshot3.png">
7. Review files that tool has produced at path you’ve selected before.
   - <img src="/screenshot/EZTGui_screenshot4.png">
 
## FAQ ##
**Q:** Can this tool be used to collect forensics artifact like KAPE?

**A:** Nope. This tool only process data/artifacts that KAPE has acquire. It’s not a tool to collect data/artifact on target host.

##
**Q:** Is this tool similar to XXX tools in the market?

**A:** This tool is NOT like XXX tools; which collected artifacts will be processed with some logic behind to produce artifact forensics report. This is just a straight forward implementation. If you run MFT processing, its MFT result that you’ll get (using MFTECmd at the back).

##
**Q:** What’s the difference/advantage of using this tool then?

**A:** To be honest, this tool actually created as I’m lazy enough to manually type in command parameter that the Eric Zimmerman tools required to processing artifact. Not to mentioned when you wrongly copy paste different KAPE path and hit ENTER too fast until you realized you using wrong artifact for wrong case that you currently investigating.

## Humble Note ##
Please bear in mind that I'm not a coder nor a software developer. I code just to make my work easier. If the codes run, its run. But I'm more than happy if anyone wanna to contribute to the tools development.
