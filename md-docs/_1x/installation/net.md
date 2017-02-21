---
id: net
title: .NET
permalink: installation/net/index.html
---

## Add Couchbase Lite to your app

### NuGet

1. In Visual Studio or Xamarin Studio, right-click on the desired project and select the menu to add a Nuget dependency.

    <img src="../img/vs-nuget.png" class=center-image />

2. Search for 'Couchbase Lite' and select the latest version of the **Couchbase.Lite** package.
3. Once Couchbase Lite is installed you can run the target with Couchbase Lite as a dependency.

#### Available packages

The following libraries are available.

|Package Name|Server|
|:-----------|:-----|
|`Couchbase.Lite.Storage.SystemSQLite`|To use SQLite as the storage type. This is the default.|
|`Couchbase.Lite.Storage.SQLCipher`|To use SQLCipher as the storage type.|
|`Couchbase.Lite.Storage.ForestDB`|To use ForestDB as the storage type.|

## Getting Started

Create a new Visual Studio or Xamarin Studio project and install Couchbase Lite by following the steps above.

<img src="../img/vs-new-project.png" class=center-image />

Open `MainWindow.xaml.cs` in Visual Studio and add the following in the `MainWindow` method.

```csharp
Manager manager = Manager.SharedInstance;

Database database = manager.GetDatabase("app");

Dictionary<string, object> properties = new Dictionary<string, object>
{
		{ "title", "Couchbase Mobile"},
		{ "sdk", "C#" }
};

Document document = database.CreateDocument();

document.PutProperties(properties);

Console.WriteLine($"Document ID :: {document.Id}");
Console.WriteLine($"Learning {document.GetProperty("title")} with {document.GetProperty("sdk")}");
```

Click the **Start** button. Notice the document ID and properties are logged to the Application Output.
