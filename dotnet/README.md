Install dotnet on ubuntu
-------------------------

* The .NET platform provides several ways to build and run applications, including web, desktop, mobile, gaming, and IoT.
  
```

wget https://packages.microsoft.com/config/ubuntu/22.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
rm packages-microsoft-prod.deb
```

install the dotnet sdk
----------------------
```
sudo apt-get update 
sudo apt-get install -y dotnet-sdk-7.0
```

* The .NET SDK allows you to develop apps with .NET. If you install the .NET SDK, you don't need to install the corresponding runtime.
  
install ASP .net core runtime
------------------------------ 

```
sudo apt-get update 
sudo apt-get install -y aspnetcore-runtime-7.0
```

* The ASP.NET Core Runtime allows you to run apps that were made with .NET that didn't provide the runtime. The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET.
``-
sudo apt-get install -y dotnet-runtime-7.0

```

* As an alternative to the ASP.NET Core Runtime, you can install the .NET Runtime, which doesn't include ASP.NET Core support: replace aspnetcore-runtime-7.0 in the previous command with dotnet-runtime-7.0