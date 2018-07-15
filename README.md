# Sotsera.Blazor.Toaster
A Blazor port of [Toastr.js](https://raw.githubusercontent.com/CodeSeven/toastr/). If there is any credit here it should go to the authors of the original library.

The sample project has been published [here](https://sotsera.github.io/sotsera.blazor.toaster/).

## Configuration

Add reference to the package.

Configure dependency injection

```c#
services.AddToaster((options) => { ... });
```

In App.cshtml

```c#
@addTagHelper *, Sotsera.Blazor.Toaster
<toastContainer />
```

## Usage

In a component

```c#
@inject Sotsera.Blazor.IToaster toaster;
```

In a class

```c#
[inject] 
Sotsera.Blazor.IToaster toaster;
```

then call one of the display methods:

```c#
toaster.Info("toast body text");
toaster.Success("toast body text");
toaster.Warning("toast body text");
toaster.Error("toast body text");
```

Each of these methods can accept a title and an action for the toast specific configuration

```c#
toaster.Info("toast body text");
toaster.Info("toast body text", "toast title");
toaster.Info("toast body text", "toast title", options =>
{
    options.Clicked += toast => Console.WriteLine($"Toast '{toast.Message}' Clicked!");
});
```

## Credits
This is a simple attempt to port [Toastr.js](https://raw.githubusercontent.com/CodeSeven/toastr/) to Blazor.

Currently the [css styles](https://github.com/CodeSeven/toastr/blob/50092cc604850a16c985520b63df184d3e0b4086/build/toastr.min.css) used are literally COPIED from Toastr.js.

## License
Sotsera.Blazor.Toaster is licensed under [MIT license](http://www.opensource.org/licenses/mit-license.php)