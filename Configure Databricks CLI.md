### Configure Databricks CLI to communicate with your workspace


The Databricks CLI (command-line interface) allows you to interact with the Databricks platform from your local terminal or automation scripts. 

The Databricks CLI commands can also be run from within a Databricks workspace using web terminal 
See: https://docs.databricks.com/aws/en/compute/web-terminal

Install Databricks CLI 
	1. On Windows, the CLI can be installed using winget which is a command line tool that enables users to search, install, manage and configure applications on Windows 10, Windows 11 and Windows Server 2025 computers. It is by default available on Windows. In other case please see: Use WinGet to install and manage applications | Microsoft Learn on how to install winget. Alternatives to Winget ( Chocolatey and Windows Subsystem for Linux (WSL))
	
	
Last resort: Install the Databricks CLI from source via Command Prompt or PowerShell

Installation using Winget
	
	1. Open Command Prompt and run the following two commands
```
winget search databricks
winget install Databricks.DatabricksCLI
```

	2. Confirm that the Databricks CLI is installed by running the following command displaying the version Databricks CLI. Current version should be 0.205.0 or above
```
databricks  -v
```

```
---------------
Databricks CLI v0.265.0
```

	3. To get started on development using the CLI, configure access to your workspace 

	For account-level operations, in the following command, replace the following placeholders:
	• Replace <account-console-url> with your Databricks https://accounts.cloud.databricks.com.
	• Replace <account-id> with your Databricks account ID. See Locate your account ID.
```
databricks auth login --host <account-console-url> --account-id <account-id>
```

	For workspace-level operations, in the following command, replace <workspace-url> with your Databricks workspace instance URL, for example https://dbc-a1b2345c-d6e7.cloud.databricks.com.
```
databricks auth login --host <workspace-url>
```

These commands prompt you to enter your Databricks username which you can find on the Web browser under your user icon. Once your username is entered, you will be redirected to your web browser with on-screen instructions to log in to your Databricks account or workspace. 
	
	4. Verify successful authentication with command 
```
databricks auth describe
```

```
-----------------------------
Host: https://dbc-xxxx.cloud.databricks.com
User: username
Authenticated with: databricks-cli
-----
Current configuration:
  ✓ host: https://dbc-xxx.cloud.databricks.com (from C:\Users\User/.databrickscfg config file)
  ✓ profile: maureen287rachel
  ✓ auth_type: databricks-cli (from C:\Users\User/.databrickscfg config file)
```

	5. Run Databricks CLI commands from command line to reverify authentication  
See list of Databricks CLI commands

References:  
1.   [Databricks CLI tutorial]([https://docs.databricks.com/](https://docs.databricks.com/aws/en/dev-tools/cli/))
 | Databricks Documentation 08-21-2025
