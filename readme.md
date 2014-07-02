#A WebApi2 IDependencyResolver wrapper for Structuremap 3.x

[**What it adds to your solution**]

2 directories to the root of your MVC project:

* App_Start (If not already in your solution)
* DependencyResolution

4 Files:

* App_Start/StructuremapWebApi.cs
* DependencyResolution/StructureMapDependencyScope.cs
* DependencyResolution/StructureMapScopeModule.cs 
* DependencyResolution/IoC.cs 
* DependencyResolution/DefaultRegistry.cs (This is where you would define your mappings)


[**Default configuration**]

	public DefaultRegistry() {
		Scan(
			scan => {
				scan.TheCallingAssembly();
				scan.WithDefaultConventions();
			});
		//For<IExample>().Use<Example>();
	}

This configuration will *just work* for any Interfaces and concrete implementations that follow the default convention and are part of the project. I.E. ISomeService.cs implemented with SomeService.cs
