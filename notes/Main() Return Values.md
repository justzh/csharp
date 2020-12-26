# Main() return values (C# Programming Guide)

The `Main` method can return `void`:

	static void Main()
	{
		// ...
	}
	
It can also return an `int`:

	static int Main()
	{
		// ...
		return 0;	
	}
	
If the return value from `Main` is not used, returning `void` allows for slightly simpler code. However, returning an integer enables the program to communicate status information to other programs or scripts that invoke the executable file. The return value from `Main` is treated as the exit code for the process. If `void` is returned from `Main`, the exit code will be implicitly `0`. The following example shows how the return value from `Main` can be accessed.

## Example

This example uses .NET Core command-line tools.

Modify the `Main` method in *program.cs* as follows:

	// Save this program as MainReturnValTest.cs.
	class MainReturnValTest
	{
		static int Main()
		{
			// ...
			return 0;
		}
	}
	
When a program is executed in Windows, any value returned from the `Main` function is stored in an environment variable. This environment variable can be retrieved used `ERRORLEVEL` from a batch file, or `$LastExitCode` from PowerShell.

You can build the application using the dotnet CLI `dotnet build` command.

Next, create a PowerShell script to run the application and display the result. Past the following code into a text file and save it as `test.ps1` in the folder that contains the project. Run the PowerShell script by typing `test.ps1` at the PowerShell prompt.