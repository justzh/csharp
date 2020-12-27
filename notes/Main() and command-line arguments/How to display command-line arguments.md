# How to display command-line arguments (C# Programming Guide)

Arguments provided to an executable on the command line are accessible through an optional parameter to `Main`. The arguments are provided in the form of an array of strings. Each element of the array contains one argument. White-space between arguments is removed. For example:

| **Input on command line** | **Array of strings passed to Main** |
|---------------------------|-------------------------------------|
| executable.exe a b c      | "a"  "b"  "c"                       |

## Example

This example displays the command-line arguments passed to a command-line application.
	
	class CommandLine
	{
		static void Main(string[] args)
		{
			// The Length property provides the number of array elements.
			Console.WriteLine($"parameter count = {args.Length}");
			
			for (int i = 0; i < args.Length; ++i)
			{
				Console.WriteLine($"Arg[{i}] = [{args[i]}]");ß
			}
		}
	}
	/* Output (assumes 3 cmd line args):
    	parameter count = 3
    	Arg[0] = [a]
    	Arg[1] = [b]
    	Arg[2] = [c]
	*/