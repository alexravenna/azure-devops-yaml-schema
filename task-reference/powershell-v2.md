---
title: PowerShell@2 - PowerShell v2 task
description: Run a PowerShell script on Linux, macOS, or Windows.
ms.date: 07/21/2025
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# PowerShell@2 - PowerShell v2 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to run a PowerShell script on Linux, macOS, or Windows.

>[!NOTE]
> By default, PowerShell v2 uses PowerShell Core for Linux agents and Windows PowerShell for Windows agents. To use the latest version of PowerShell on Windows agents, set the `pwsh` parameter to `true`. PowerShell Core will then be used instead.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022.1"

```yaml
# PowerShell v2
# Run a PowerShell script on Linux, macOS, or Windows.
- task: PowerShell@2
  inputs:
    #targetType: 'filePath' # 'filePath' | 'inline'. Type. Default: filePath.
    filePath: # string. Required when targetType = filePath. Script Path. 
    #arguments: # string. Optional. Use when targetType = filePath. Arguments. 
    #script: # string. Required when targetType = inline. Script. 
  # Preference Variables
    #errorActionPreference: 'stop' # 'default' | 'stop' | 'continue' | 'silentlyContinue'. ErrorActionPreference. Default: stop.
    #warningPreference: 'default' # 'default' | 'stop' | 'continue' | 'silentlyContinue'. WarningPreference. Default: default.
    #informationPreference: 'default' # 'default' | 'stop' | 'continue' | 'silentlyContinue'. InformationPreference. Default: default.
    #verbosePreference: 'default' # 'default' | 'stop' | 'continue' | 'silentlyContinue'. VerbosePreference. Default: default.
    #debugPreference: 'default' # 'default' | 'stop' | 'continue' | 'silentlyContinue'. DebugPreference. Default: default.
    #progressPreference: 'silentlyContinue' # 'default' | 'stop' | 'continue' | 'silentlyContinue'. ProgressPreference. Default: silentlyContinue.
  # Advanced
    #failOnStderr: false # boolean. Fail on Standard Error. Default: false.
    #showWarnings: false # boolean. Show warnings as Azure DevOps warnings. Default: false.
    #ignoreLASTEXITCODE: false # boolean. Ignore $LASTEXITCODE. Default: false.
    #pwsh: false # boolean. Use PowerShell Core. Default: false.
    #workingDirectory: # string. Working Directory. 
    #runScriptInSeparateScope: false # boolean. Run script in the separate scope. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2022"

```yaml
# PowerShell v2
# Run a PowerShell script on Linux, macOS, or Windows.
- task: PowerShell@2
  inputs:
    #targetType: 'filePath' # 'filePath' | 'inline'. Type. Default: filePath.
    filePath: # string. Required when targetType = filePath. Script Path. 
    #arguments: # string. Optional. Use when targetType = filePath. Arguments. 
    #script: # string. Required when targetType = inline. Script. 
  # Preference Variables
    #errorActionPreference: 'stop' # 'default' | 'stop' | 'continue' | 'silentlyContinue'. ErrorActionPreference. Default: stop.
    #warningPreference: 'default' # 'default' | 'stop' | 'continue' | 'silentlyContinue'. WarningPreference. Default: default.
    #informationPreference: 'default' # 'default' | 'stop' | 'continue' | 'silentlyContinue'. InformationPreference. Default: default.
    #verbosePreference: 'default' # 'default' | 'stop' | 'continue' | 'silentlyContinue'. VerbosePreference. Default: default.
    #debugPreference: 'default' # 'default' | 'stop' | 'continue' | 'silentlyContinue'. DebugPreference. Default: default.
  # Advanced
    #failOnStderr: false # boolean. Fail on Standard Error. Default: false.
    #showWarnings: false # boolean. Show warnings as Azure DevOps warnings. Default: false.
    #ignoreLASTEXITCODE: false # boolean. Ignore $LASTEXITCODE. Default: false.
    #pwsh: false # boolean. Use PowerShell Core. Default: false.
    #workingDirectory: # string. Working Directory. 
    #runScriptInSeparateScope: false # boolean. Run script in the separate scope. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020.1"

```yaml
# PowerShell v2
# Run a PowerShell script on Linux, macOS, or Windows.
- task: PowerShell@2
  inputs:
    #targetType: 'filePath' # 'filePath' | 'inline'. Type. Default: filePath.
    filePath: # string. Required when targetType = filePath. Script Path. 
    #arguments: # string. Optional. Use when targetType = filePath. Arguments. 
    #script: # string. Required when targetType = inline. Script. 
    #errorActionPreference: 'stop' # 'stop' | 'continue' | 'silentlyContinue'. ErrorActionPreference. Default: stop.
  # Advanced
    #failOnStderr: false # boolean. Fail on Standard Error. Default: false.
    #showWarnings: false # boolean. Show warnings as Azure DevOps warnings. Default: false.
    #ignoreLASTEXITCODE: false # boolean. Ignore $LASTEXITCODE. Default: false.
    #pwsh: false # boolean. Use PowerShell Core. Default: false.
    #workingDirectory: # string. Working Directory.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020"

```yaml
# PowerShell v2
# Run a PowerShell script on Linux, macOS, or Windows.
- task: PowerShell@2
  inputs:
    #targetType: 'filePath' # 'filePath' | 'inline'. Type. Default: filePath.
    filePath: # string. Required when targetType = filePath. Script Path. 
    #arguments: # string. Optional. Use when targetType = filePath. Arguments. 
    #script: # string. Required when targetType = inline. Script. 
    #errorActionPreference: 'stop' # 'stop' | 'continue' | 'silentlyContinue'. ErrorActionPreference. Default: stop.
  # Advanced
    #failOnStderr: false # boolean. Fail on Standard Error. Default: false.
    #ignoreLASTEXITCODE: false # boolean. Ignore $LASTEXITCODE. Default: false.
    #pwsh: false # boolean. Use PowerShell Core. Default: false.
    #workingDirectory: # string. Working Directory.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="targetType"::: -->
:::moniker range="<=azure-pipelines"

**`targetType`** - **Type**<br>
`string`. Allowed values: `filePath` (File Path), `inline`. Default value: `filePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the type of script for the task to run: an inline script or a path to a `.ps1` file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="filePath"::: -->
:::moniker range="<=azure-pipelines"

**`filePath`** - **Script Path**<br>
`string`. Required when `targetType = filePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path of the script to execute. Must be a fully qualified path or relative to `$(System.DefaultWorkingDirectory)`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range="<=azure-pipelines"

**`arguments`** - **Arguments**<br>
`string`. Optional. Use when `targetType = filePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the arguments passed to the PowerShell script. Arguments can be ordinal parameters or named parameters. For example, `-Name someName -Path -Value "Some long string value"`.

`arguments` is not used when `targetType` is set to `inline`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="script"::: -->
:::moniker range="<=azure-pipelines"

**`script`** - **Script**<br>
`string`. Required when `targetType = inline`. Default value: `# Write your PowerShell commands here.\n\nWrite-Host "Hello World"`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the contents of the script. The maximum supported inline script length is 20000 characters. Use a script from a file if you want to use a longer script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="errorActionPreference"::: -->
:::moniker range=">=azure-pipelines-2022"

**`errorActionPreference`** - **ErrorActionPreference**<br>
`string`. Allowed values: `default`, `stop`, `continue`, `silentlyContinue`. Default value: `stop`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Prepends the line `$ErrorActionPreference = 'VALUE'` at the top of your script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

**`errorActionPreference`** - **ErrorActionPreference**<br>
`string`. Allowed values: `stop`, `continue`, `silentlyContinue`. Default value: `stop`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Prepends the line `$ErrorActionPreference = 'VALUE'` at the top of your script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="warningPreference"::: -->
:::moniker range=">=azure-pipelines-2022"

**`warningPreference`** - **WarningPreference**<br>
`string`. Allowed values: `default`, `stop`, `continue`, `silentlyContinue`. Default value: `default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When not set to  `Default`, prepends the line `$WarningPreference = 'VALUE'` at the top of your script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="informationPreference"::: -->
:::moniker range=">=azure-pipelines-2022"

**`informationPreference`** - **InformationPreference**<br>
`string`. Allowed values: `default`, `stop`, `continue`, `silentlyContinue`. Default value: `default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When not set to `Default`, prepends the line `$InformationPreference = 'VALUE'` at the top of your script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="verbosePreference"::: -->
:::moniker range=">=azure-pipelines-2022"

**`verbosePreference`** - **VerbosePreference**<br>
`string`. Allowed values: `default`, `stop`, `continue`, `silentlyContinue`. Default value: `default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When not set to `Default`, prepends the line `$VerbosePreference = 'VALUE'` at the top of your script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="debugPreference"::: -->
:::moniker range=">=azure-pipelines-2022"

**`debugPreference`** - **DebugPreference**<br>
`string`. Allowed values: `default`, `stop`, `continue`, `silentlyContinue`. Default value: `default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When not set to `Default`, prepends the line `$DebugPreference = 'VALUE'` at the top of your script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="progressPreference"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`progressPreference`** - **ProgressPreference**<br>
`string`. Allowed values: `default`, `stop`, `continue`, `silentlyContinue`. Default value: `silentlyContinue`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When not set to `Default`, prepends the line `$ProgressPreference = 'VALUE'` at the top of your script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failOnStderr"::: -->
:::moniker range="<=azure-pipelines"

**`failOnStderr`** - **Fail on Standard Error**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If the value of this boolean is `true`, the task fails if any errors are written to the error pipeline or if any data is written to the Standard Error stream. Otherwise, the task relies on the exit code to determine failure.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="showWarnings"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`showWarnings`** - **Show warnings as Azure DevOps warnings**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If the value is set to `true`, and your script writes warnings, then the warnings will appear as warnings in Pipeline logs.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ignoreLASTEXITCODE"::: -->
:::moniker range="<=azure-pipelines"

**`ignoreLASTEXITCODE`** - **Ignore $LASTEXITCODE**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If the value is set to `false`, the line `if ((Test-Path -LiteralPath variable:\LASTEXITCODE)) { exit $LASTEXITCODE }` is appended to the end of your script. This will cause the last exit code from an external command to be propagated as the exit code of `powershell`. Otherwise, the line is not appended to the end of your script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pwsh"::: -->
:::moniker range="<=azure-pipelines"

**`pwsh`** - **Use PowerShell Core**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this is true, then tasks running on Windows agents will use `pwsh.exe` from your path instead of `powershell.exe`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`workingDirectory`** - **Working Directory**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the working directory where the script is run. If a value is not specified, the working directory is `$(Build.SourcesDirectory)`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runScriptInSeparateScope"::: -->
:::moniker range=">=azure-pipelines-2022"

**`runScriptInSeparateScope`** - **Run script in the separate scope**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This input allows executing PowerShell scripts using `&` operator instead of the default `.`. If this input is set to `true`, the script will be executed in a separate scope, and globally scoped PowerShell variables won't be updated.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="<=azure-pipelines"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Each PowerShell session lasts only for the duration of the job in which it runs. Tasks that depend on what has been bootstrapped must be in the same job as the bootstrap.

### Task shortcuts

`PowerShell@2` has two shortcuts in YAML: [steps.powershell](/azure/devops/pipelines/yaml-schema/steps-powershell) and [steps.pwsh](/azure/devops/pipelines/yaml-schema/steps-pwsh).

* `powershell` runs using either Windows PowerShell (on Windows) or `pwsh` (Linux and macOS).
* `pwsh` runs PowerShell Core, the cross-platform edition of PowerShell built on .NET Core.

```yml
steps:
- powershell: # Run a script in Windows PowerShell on Windows, and pwsh on Linux and macOS.
- pwsh: # Run a script in PowerShell Core on Windows, macOS, and Linux.
```

### Set a variable so it can be read by subsequent scripts and tasks

To learn more about defining build variables in a script, see [Define and modify your build variables in a script](/azure/devops/pipelines/process/variables#set-a-multi-job-output-variable).

To learn more about defining release variables in a script, see [Define and modify your release variables in a script](/azure/devops/pipelines/release/variables#use-custom-variables).

### Passing pipeline secrets in script, but secret is not masked in pipeline logs

Be aware that PowerShell cuts off error messages, so if you use pipeline secrets in a script, the secrets could be trimmed and exposed. For example, in the inline script below:

```powershell
./script.ps1 --arg1 value1 --arg2 <some_secret_which_will_be_masked_here>
```

There could be an exception like: `At <path_to_temp_script_file>:4 char:3`:

```powershell
+   ./script.ps1 --arg1 value1 --arg2 <unmasked_part_of_original_secret> ...
+   ~~~~~~~~~~
    + <Additional exception details>
```

To avoid this issue, you can handle these exceptions on a script level, or avoid cases when pipeline secrets could appear in source code lines within error messages.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

* [Invoke a script from a file](#invoke-a-script-from-a-file)
* [Write a warning](#write-a-warning)
* [Write an error](#write-an-error)
* [Call PowerShell script with multiple arguments](#call-powershell-script-with-multiple-arguments)

### Invoke a script from a file

The following is a sample PowerShell file named `test.ps1` located in the root of your repository.

```powershell
Write-Host "Hello World from $Env:AGENT_NAME."
Write-Host "My ID is $Env:AGENT_ID."
Write-Host "AGENT_WORKFOLDER contents:"
gci $Env:AGENT_WORKFOLDER
Write-Host "AGENT_BUILDDIRECTORY contents:"
gci $Env:AGENT_BUILDDIRECTORY
Write-Host "BUILD_SOURCESDIRECTORY contents:"
gci $Env:BUILD_SOURCESDIRECTORY
Write-Host "Over and out."
```

You can invoke this script in your pipeline like this.

```yml
steps:
- task: PowerShell@2
  inputs:
    targetType: 'filePath'
    filePath: 'test.ps1'
```

### Write a warning

```yml
- task: PowerShell@2
  inputs:
    targetType: 'inline'
    script: Write-Host "##vso[task.LogIssue type=warning;]This is the warning"
    # Writes a warning to build summary and to log in yellow text
```

### Write an error

```yml
- task: PowerShell@2
  inputs:
    targetType: 'inline'
    script: Write-Host "##vso[task.LogIssue type=error;]This is the error"
    # Writes an error to build summary and to log in red text
```

If you want this error to fail the build, add `exit 1` to the script.

```yml
- task: PowerShell@2
  inputs:
    targetType: 'inline'
    script: |
      Write-Host "##vso[task.LogIssue type=error;]This is the error"
      exit 1
    # Writes an error to build summary and to log in red text
```

### Call PowerShell script with multiple arguments

Create PowerShell script `test2.ps1`:

```powershell
param ($input1, $input2)
Write-Host "$input1 $input2"
```

In your YAML pipeline, call:

```yaml
- task: PowerShell@2
  inputs:
    targetType: 'filePath'
    filePath: $(System.DefaultWorkingDirectory)\test2.ps1
    arguments: > # Use this to avoid newline characters in multiline string
      -input1 "Hello"
      -input2 "World"
  displayName: 'Print Hello World'
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="<=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.115.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [Use a PowerShell script to customize your pipeline - ApplyVersionToAssemblies.ps1](/azure/devops/pipelines/scripts/powershell)
* Learn more about PowerShell scripts
  * [Scripting with Windows PowerShell](/powershell/scripting/overview)
  * [Microsoft Script Center (the Scripting Guys)](https://technet.microsoft.com/scriptcenter/bb410849.aspx)
  * [PowerShell.org](https://powershell.org/)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
