# VSCode for win32app Devops using PADT

1. Install [Sandbox](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-sandbox/windows-sandbox-overview) with powershell.
```powershell
Get-WindowsOptionalFeature -FeatureName "Containers-DisposableClientVM" -Online
Enable-WindowsOptionalFeature -FeatureName "Containers-DisposableClientVM" -Online
```

2. Install [VSCode](https://code.visualstudio.com/) with [Winget](https://docs.microsoft.com/en-us/windows/package-manager/winget/)
```powershell
winget install Microsoft.VisualStudioCode
```

3. Install [GitHub CLI](https://cli.github.com/) with [Winget](https://docs.microsoft.com/en-us/windows/package-manager/winget/)
```powershell
winget install GitHub.cli
```

4. Open VSCode and initiate a Terminal `(CTRL + J)`
5. Install [GitHub CLI](https://cli.github.com/) with [Winget](https://docs.microsoft.com/en-us/windows/package-manager/winget/). Initialise the repo and clone it locally. *(optional, just demo showing possiblities)*
```powershell
# Install cli
winget install GitHub.cli

# Fork PSAppDeployToolkit and clone it locally
gh repo fork https://github.com/PSAppDeployToolkit/PSAppDeployToolkit --clone

# Open the fork in vscode
code -r PSAppDeployToolkit
```

# Create a branch
git checkout -b devops

6. Initialise the workspace
```powershell
# Workspace settings including build tasks
New-Item -Path ".vscode" -ItemType Directory
```

8. Prepare devops.

- [.vscode\Build.ps1](https://github.com/MEConfigMgr/PSAppDeployToolkit/edit/master/.vscode/Build.ps1)
- [.vscode\Global.ps1](https://github.com/MEConfigMgr/PSAppDeployToolkit/edit/master/.vscode/Global.ps1)
- [.vscode\LogonCommand.ps1](https://github.com/PSAppDeployToolkit/vscode/edit/master/.vscode/LogonCommand.ps1)
- [.vscode\Sandbox.ps1](https://github.com/MEConfigMgr/PSAppDeployToolkit/edit/master/.vscode/Sandbox.ps1)
- [.vscode\tasks.json](https://github.com/MEConfigMgr/PSAppDeployToolkit/edit/master/.vscode/tasks.json)

9. Speed up ops
- [.vscode\Workspace.code-snippets.json](https://github.com/MEConfigMgr/PSAppDeployToolkit/edit/master/.vscode/Workspace.code-snippets.json)
- [PSAppDeployToolkit.code-workspace](https://github.com/MEConfigMgr/PSAppDeployToolkit/edit/master/PSAppDeployToolkit.code-workspace)

### Other interesting ideas.

- [Preload winget into the Sandbox base image](https://github.com/microsoft/winget-pkgs/discussions/56530) by [Trenly](https://github.com/Trenly)
- [Automate the upload to Intune](https://github.com/FlorianSLZ/scloud/tree/main/intune-win32-deployment) by [FlorianSLZ](https://github.com/FlorianSLZ)