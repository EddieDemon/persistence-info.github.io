The repository tries to gather an information about persistence mechanisms to make the protection/detection more efficient. Most of the information is well known for years, being actively used within various scenarios. 

## Definitions:
1. Persistence mechanism - configuration change, making the arbitrary code to run automatically, or in a way making it likely to happen unexpectedly due to typical user actions such as right-click on files etc.
1. Configuration change - change of a file content, registry settings, database data, etc.
1. Scope - Windows systems currently supported or popular. Exceptions may happen if the mechanism relies on very common non-OS dependencies such as Microsoft Office, Google Chrome etc.
1. Exclusions - replacement of a binary file with another binary file may count as a persistence mechanism, but will be not reflected in the repository as possibilities are endless and not really interesting.
1. Entries are defined by the configuration change LOCATION, not the configuration change itself. Two very different entries within the Run registry key count as one persistence mechanism. 

## Classification:
1. Permissions
    1. End-user - standard user permissions are good enough to create the persistence
    1. Admin - standard user permissions are NOT good enough to create the persistence
1. Security context
    1. User - code runs as the user being logged-on within the user session
    1. System - code runs as the localsystem
    1. Other - code runs in the security context not described above
1. Persistence type
    1. Files only - it is enough to drop a file to make code run
    1. Registry - reasonably simple registry changes are required to make code run
    1. Other - something more than registry and files is required
1. Code type
    1. EXE - EXE file is executed as a new process
    1. DLL - DLL is loaded by a processes (not being result of any persistence mechanism) in a way making code run.
    1. Other - scripts etc.
    1. Fileless - no new files are put on disk to create a persistence mechanisms
1. Launch type
    1. Automatic - it is enough to start windows to make code run
    1. Logon required - user must log on to make code run
    1. User initiated - user must log on and perform some actions to make code run
1. Impact
    1. Destructive - typical OS functionalities are negatively affected by creating a persistence mechanism
    1. Non-destructive - typical OS functionalities are NOT negatively affected by creating a persistence mechanism
 1. OS version
    1. All OS versions - it is enough to have any current Windows version
    1. Selected OS versions - especially when the persistence exists within the Windows Server only
1. Dependencies
    1. OS Only - standard OS installation is enough to make persistence happen
    1. Additional components required - some unusual Windows components are required, such as server roles, non-standard features etc
    1. Additional software required - non-OS software components are required to make persistence method work
1. Toolset
    1. OS only, scriptable - built-in OS tools and zero clicking is enough to create a persistence
    1. PowerShell - built-in OS tools are not enough but PowerShell can do the job and the script exists
    1. OS only, non-scriptable  - built-in OS tools only, but some clicking is required to create a persistence
    1. Own toolkit required - anything else

