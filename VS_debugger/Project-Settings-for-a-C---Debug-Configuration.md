---
title: "Project Settings for a C++ Debug Configuration"
ms.custom: na
ms.date: 10/07/2016
ms.devlang: 
  - FSharp
  - VB
  - CSharp
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - vs-ide-debug
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 860c7f13-a108-4fe5-8fca-d235cd3ca1cb
caps.latest.revision: 49
manager: ghogen
translation.priority.ht: 
  - cs-cz
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pl-pl
  - pt-br
  - ru-ru
  - tr-tr
  - zh-cn
  - zh-tw
---
# Project Settings for a C++ Debug Configuration
You can change the project settings for a C or Visual C++ debug configuration in the **Property Pages** dialog box, as discussed in [How to: Set Debug and Release Configurations](../VS_debugger/How-to--Set-Debug-and-Release-Configurations.md). The following tables show where to find debugger-related settings in the **Property Pages** dialog box.  
  
> [!WARNING]
>  The debug project settings in the **Configuration Properties/Debugging** category for Windows Store apps and components that are written in C++ are different. See [Start a debug session (VB, C#, C++ and XAML)](../VS_debugger/Start-a-debugging-session-for-a-Store-app-in-Visual-Studio--VB--C#--C---and-XAML-.md) in the Windows Development Center.  
  
 Specify which debugger to use in the **Debugger to launch** list box. Your choice will affect which properties are visible.  
  
 Each debug property setting is automatically written and saved to the "per-user" file (.vcxproj.user) for your solution whenever you save your solution.  
  
### Configuration Properties folder (Debugging category)  
  
|**Setting**|**Description**|  
|-----------------|---------------------|  
|**Debugger to launch**|Specifies the debugger to run, with the following choices:<br /><br /> -   **Local Windows Debugger**<br />-   **Remote Windows Debugger**<br />-   **Web Browser Debugger**<br />-   **Web Service Debugger**|  
|**Command** (Local Windows Debugger)|Specifies the command for starting the program that you are debugging on the local computer.|  
|**Remote Command** (Remote Windows Debugger)|The path for the .exe on the remote computer. Enter the path just as you would enter it on the remote machine.|  
|**Command Arguments** (Local Windows Debugger and Remote Windows Debugger)|-   Specifies arguments for the command specified earlier.<br /><br /> You can use the following redirection operators in this box:<br /><br /> < `file`<br /> Reads stdin from file.<br /><br /> > `file`<br /> Writes stdout to file.<br /><br /> >> `file`<br /> Appends stdout to file.<br /><br /> 2> `file`<br /> Writes stderr to file.<br /><br /> 2>> `file`<br /> Appends stderr to file.<br /><br /> 2> &1<br /> Sends stderr (2) output to same location as stdout (1).<br /><br /> 1> &2<br /> Sends stdout (1) output to same location as stderr (2).<br /><br /> In most cases, these operators are applicable only to console applications.|  
|**Working Directory**|Specifies the working directory of the program being debugged, relative to the project directory where your EXE is located. If you leave this blank, the working directory is the project directory. For remote debugging, the project directory will be on the remote server.|  
|**Attach** (Local Windows Debugger and Remote Windows Debugger)|Specifies whether to start or attach to the application. Default setting is No.|  
|**Remote Server Name** (Remote Windows Debugger)|Specifies the name of a computer (other than yours) on which you want to debug an application.<br /><br /> The RemoteMachine Build macro is set to the value of this property; for more information, see [Macros for Build Commands and Properties](../Topic/Common%20Macros%20for%20Build%20Commands%20and%20Properties.md).|  
|**Connection** (Remote Windows Debugger)|Allows you to switch between standard and no-authentication connection types for remote debugging. Specify a remote computer name in the **Remote Server Name** box. Connection types include the following:<br /><br /> -   **Remote with Windows Authentication**<br />-   **Remote with No Authentication (Native Only)**<br /><br /> **Note** Remote debugging with No Authentication may leave the remote computer vulnerable to security violations. Windows Authentication mode is more secure.<br /><br /> For more information, see [Remote Debugging Setup](../VS_debugger/Remote-Debugging.md).|  
|**HTTP URL** (Web Service Debugger and Web Browser Debugger)|Specifies the URL where the project you are debugging is located.|  
|**Debugger Type**|Specifies the type of debugger to be used: **Native Only**, **Managed Only**, **GPU Only**, **Mixed**, **Auto** (default), or **Script**.<br /><br /> -   **Native Only** is for unmanaged C++ code.<br />-   **Managed Only** is for code that runs under the common language runtime (managed code).<br />-   **Mixed** invokes debuggers for both managed and unmanaged code.<br />-   **Auto** determines the debugger type based on compiler and EXE information.<br />-   **Script** invokes a debugger for scripts.<br />-   **GPU Only** is for C++ AMP code that runs on a GPU device or on the DirectX reference rasterizer. See [Debugging GPU Code](../VS_debugger/Debugging-GPU-Code.md).|  
|**Environment** (Local Windows Debugger)|Specifies environment variables for the program that you are debugging. Use standard environment variable syntax (for example, `PATH="%SystemRoot%\..."`). These variables override the system environment or are merged with the system environment, depending on the **Merge Environment** setting. When you click in the settings column, an "Edit…" appears. Click that link to edit environment variables.|  
|**Merge Environment** (Local Windows Debugger)|Determines whether the variables that are specified in the **Environment** box will be merged with the environment that is defined by the operating system. Default setting is Yes.|  
|**SQL Debugging** (all but MPI Cluster Debugger)|Enables debugging of SQL procedures from your Visual C++ application. Default setting is No.|  
|**Debugging Accelerator Type** (GPU debugging only)|Specifies the GPU device to use for debugging. Installing device drivers for compatible GPU devices will add additional options. The default setting is "GPU - Software Emulator."|  
|**GPU Default Breakpoint Behavior** (GPU debugging only)|Specifies whether a breakpoint event should be raised for each thread in a SIMD warp. The default setting is to raise the breakpoint event only once per warp.|  
|**Amp Default Accelerator** (GPU debugging only)|Specifies the default AMP accelerator when debugging GPU code. Choose **WARP software accelerator** to investigate if an issue is caused by the hardware or a driver instead of your code.|  
|**Deployment Directory** (Remote Windows Debugger)|Specifies the path on the remote computer where the project output will be copied prior to launch. The path can be a network share on the remote computer, or it can be a path to a folder on the remote computer. The default setting is empty, which means the project output is not copied to a network share. To enable deployment of the files, you must also select the **Deploy** check box in the Configuration Manager dialog box. For more information, see [How to: Create and Edit Configurations](../VS_IDE/How-to--Create-and-Edit-Configurations.md).|  
|**Additional Files to Deploy** (Remote Windows Debugger)|If the Deployment Directory property is set, this is a semi-colon delimited list of additional files to copy to the deployment directory. The default setting is empty, which means that no additional files are copied to the deployment directory. To enable deployment of the files, you must also select the **Deploy** check box in the Configuration Manager dialog box. For more information, see [How to: Create and Edit Configurations](../VS_IDE/How-to--Create-and-Edit-Configurations.md).|  
|**Deploy Visual C++ Debug Runtime Libraries** (Remote Windows Debugger)|If the Deployment Directory property is set, this specifies whether the Visual C++ debug runtime libraries for the current platform should be copied to the network share. The default setting is Yes.|  
  
### C/C++ folder (General category)  
  
|Setting|Description|  
|-------------|-----------------|  
|**Debug Information Format** ([/Z7, /Zd, Zi, /ZI](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md))|Specifies the type of debug information to be created for the project.<br /><br /> The default option (/ZI) creates a program database (PDB) in Edit and Continue compatible format. For more information, see [/Z7, /Zd, /Zi, /ZI (Debug Information Format)](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md).|  
  
### C/C++ folder (Optimization category)  
  
|Setting|Description|  
|-------------|-----------------|  
|**Optimization**|Specifies whether the compiler should optimize the code it produces. Optimization changes the code that is executed. Optimized code no longer matches the source code. Therefore, debugging is difficult.<br /><br /> The default option (**Disabled (/0d**) suppresses optimization. You can develop with optimization suppressed, and then turn it on when you create the production version of your code.|  
  
### Linker folder (Debugging category)  
  
|Setting|Description|  
|-------------|-----------------|  
|**Generate Debug Info** ([/DEBUG](../Topic/-DEBUG%20\(Generate%20Debug%20Info\).md))|Tells the linker to include debug information, which will have the format specified by /Z7, /Zd, Zi, or /ZI.|  
|**Generate Program Database File** ([/PDB:name](../Topic/-PDB%20\(Use%20Program%20Database\).md))|Specify the name of a PDB file in this box. You must select ZI or /Zi for Debug Information Format.|  
|**Strip Private Symbols** ([/PDBSTRIPPED:filename](../Topic/-PDBSTRIPPED%20\(Strip%20Private%20Symbols\).md))|Specify the name of a PDB file in this box if you do not want to include private symbols in the PDB file. This option creates a second program database (PDB) file when you build your program image with any of the compiler or linker options that generate a PDB file, such as /DEBUG, /Z7, /Zd. Or /Zi. This second PDB file omits symbols that you would not want to ship to your customers. For more information, see [/PDBSTRIPPED (Strip Private Symbols)](../Topic/-PDBSTRIPPED%20\(Strip%20Private%20Symbols\).md).|  
|**Generate Map File** ([/MAP](../Topic/-MAP%20\(Generate%20Mapfile\).md))|Tells the linker to generate a map file during linking. Default setting is No. For more information, see [/MAP (Generate Mapfile)](../Topic/-MAP%20\(Generate%20Mapfile\).md).|  
|**Map File Name** ([/MAP:](../Topic/-MAP%20\(Generate%20Mapfile\).md)*name*)|If you choose Generate Map File, you can specify the map file in this box. For more information, see [/MAP (Generate Mapfile)](../Topic/-MAP%20\(Generate%20Mapfile\).md).|  
|**Map Exports** ([/MAPINFO:EXPORTS](../Topic/-MAPINFO%20\(Include%20Information%20in%20Mapfile\).md))|Includes exported functions in the map file. Default setting is No. For more information, see [/MAPINFO (Include Information in Mapfile)](../Topic/-MAPINFO%20\(Include%20Information%20in%20Mapfile\).md).|  
|**Debuggable Assembly** ([/ASSEMBLYDEBUG](../Topic/-MAPINFO%20\(Include%20Information%20in%20Mapfile\).md))|Specifies settings for the Linker /ASSEMBLYDEBUG option. Possible values are as follows:<br /><br /> -   **No debuggable attribute emitted**.<br />-   **Runtime tracking and disable optimizations (/ASSEMBLYDEBUG)**. This is the default setting,<br />-   **No runtime tracking and enable optimizations(/ASSEMBLYDEBUG:DISABLE)**.<br />-   **<inherit from parent or project defaults\>**.<br />-   For more information, see [/ASSEMBLYDEBUG (Add DebuggableAttribute)](../Topic/-ASSEMBLYDEBUG%20\(Add%20DebuggableAttribute\).md).|  
  
 You can change these settings in the Configuration Properties folder (Debug category) programmatically by using the Microsoft.VisualStudio.VCProjectEngine.VCDebugSettings interface. For more information, see <xref:Microsoft.VisualStudio.VCProjectEngine.VCDebugSettings?qualifyHint=False>.  
  
## See Also  
 [Debugging Native Code](../VS_debugger/Debugging-Native-Code.md)   
 [Debugger Settings and Preparation](../VS_debugger/Debugger-Settings-and-Preparation.md)   
 [Creating and Managing Visual C++ Projects](../Topic/Creating%20and%20Managing%20Visual%20C++%20Projects.md)   
 [/ASSEMBLYDEBUG (Add DebuggableAttribute)](../Topic/-ASSEMBLYDEBUG%20\(Add%20DebuggableAttribute\).md)   
 [Common Macros for Build Commands and Properties](../Topic/Common%20Macros%20for%20Build%20Commands%20and%20Properties.md)