# Command-Line Arguments (C# Programming Guide)

You can send arguments to the `Main` method by defining the method in one of the following ways:

	static int Main(string[] args)

	static void Main(string[] args)
	
The parameter of the `Main` method is a string array that represents the command-line arguments. Usually you determine whether arguments exist by testing the `Length` property. For example:

	if (args.Length == 0)
	{
		System.Console.WriteLine("Please enter a numeric argument.");
		return 1;
	}
	
Note that the `args` array cannot be null. So, it's safe to access the `Length` property without null checking.

You can also convert the string arguments to numeric types by using the Convert class or the `Parse` method. For example, the following statemnet convert the `string` to a `long` number by using the Parse method:

	long num = Int64.Parse(args[0]);
	
It is also possible to use the C# type `long`, which aliases `Int64`:

	long num = long.Parse(args[0]);
	
You can also the the `Convert` class method `ToInt64` to do the same thing:

	long num = Convert.ToInt64(s);