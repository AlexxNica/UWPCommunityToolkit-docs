---
permalink: /en-US/helpers/storage.htm
title: StorageService 
description: Service that will help you handle storage of generic objects within UWP applications, both locally and across all devices (roaming)
keywords: windows, app, toolkit, UWP, helpers, storage, save, read, generic objects
layout: api
search.product: eADQiWindows 10XVcnh
lang: en-us
---

## StorageService

The StorageService is a service that will help you handle storage of generic objects within UWP applications, both locally and across all devices (roaming).

## Example

{% highlight csharp %}

    var localStorageService = new LocalStorageService();
    var roamingStorageService = new RoamingStorageService();

    // Read and Save with simple objects
    string keySimpleObject = "simple";
    string result = localStorageService.Read<string>(keySimpleObject);
    localStorageService.Save(keySimpleObject, 47);

    // Read and Save with complex/large objects
    string keyLargeObject = "large";
    var result = localStorageService.ReadFileAsync<MyLargeObject>(keyLargeObject);

    var o = new MyLargeObject
    {
        ...
    };
    localStorageService.SaveFileAsync(keySimpleObject, o);

    // Complex object
    public class MyLargeObject
    {
        public string MyContent { get; set; }
        public List<string> MyContents { get; set; }
        public List<MyLargeObject> MyObjects { get; set; }
    }

{% endhighlight %}

## Requirements (Windows 10 Device Family)

| [Device family](http://go.microsoft.com/fwlink/p/?LinkID=526370) | Universal, 10.0.10586.0 or higher |
| Namespace | Microsoft.Toolkit.Uwp |

## API
* [StorageService source code](https://github.com/Microsoft/UWPCommunityToolkit/blob/master/Microsoft.Toolkit.Uwp/Helpers/Storage/StorageService.cs)
* [StorageService API documentation]({{site.baseurl}}/{{page.lang}}/api/Microsoft_Toolkit_Uwp_StorageService.htm)
