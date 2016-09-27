---
permalink: /en-US/services/microsoftgraph.htm
title: MicrosoftGraph Service
description: Easily add support for Office 365 Microsoft Graph API within your UWP Applications
keywords: windows, Microsoft Graph, Azure Active Directory, ADAL.NET, UWP, O365  
layout: api
search.product: eADQiWindows 10XVcnh
lang: en-us
---

# MicrosoftGraph Service

The **MicrosoftGraph** Service aim to easily logon to Office 365 Service in order to: 

* Retrieve User Information
* Retrieve and Send emails

## Prerequisites

### 1. Get and Office 365 Subscription

If you don't have one, you need to create an Office 365 Developer Site. There are several ways to create one:

* [An MSDN subscription](https://msdn.microsoft.com/subscriptions/manage/default.aspx) - This is available to MSDN subscribers with Visual Studio Ultimate and Visual Studio Premium.
* [An existing Office 365 subscription](https://msdn.microsoft.com/library/2ec857d5-dc6f-4cf6-ba45-adc845ef2a25%28Office.15%29.aspx) - You can use an existing Office 365 subscription, which can be any of the following: Office 365 Midsize Business, Office 365 Enterprise, Office 365 Education, Office 365 Government.
* [Free O365 trial](https://portal.office.com/Signup?OfferId=6881A1CB-F4EB-4db3-9F18-388898DAF510&DL=DEVELOPERPACK&ali=1) - You can start with a free 30-day trial, or buy an Office 365 developer subscription.
* [Free O365 Developer](http://dev.office.com/devprogram) - Or Get a One year free Office 365 Developer account
 
### 2. Register you application in Azure Active Directory

To authenticate your app, you need to register your app with Azure AD, and provide some details about your app. You can register your app manually by using the [Azure Management Portal](manage.windowsazure.com), or by using Visual Studio.

To register your app manually, see [Manually register your app with Azure AD so it can access Office 365 APIs.](https://msdn.microsoft.com/en-us/office/office365/howto/add-common-consent-manually)

To register your app by using Visual Studio, see [Using Visual Studio to register your app and add Office 365 APIs.](https://msdn.microsoft.com/office/office365/HowTo/adding-service-to-your-Visual-Studio-project)

After you've registered your app, Azure AD will generate a client ID for your app. You'll need to use this client ID to get your access token.

When you register your app in the [Azure Management Portal](manage.windowsazure.com), you will need to configure details about your application with the following steps:

1. Specify your application as a **Native Client Application**
2. Specify the Redirect Uri as **urn:ietf:wg:oauth:2.0:oob**
3. Add Application: Choose **Microsoft Graph** API 
4. Specify the permission levels the MicrosoftGraph Service requires from the Office 365 API (Microsoft Graph). Choose at least:
   * **Sign in and read user profile** to access user's profile.
   * **Read user mail and Send mail as user** to retrieve/send messages.

**Note:** Once register copy and save the Client ID for futur use.
 
|Setting|Value|
|----------|:-------------:|------:|
|Native Client Application|Yes|
|Redirect Uri|urn:ietf:wg:oauth:2.0:oob|
|Resource to Add|Microsoft Graph|
|Delegate Permissions |Sign in and read user profile, Read user mail and Send mail|


## Syntax

### Sign in with an Office 365 account

{% highlight csharp %}

// Initialize the service
if (!MicrosoftGraphService.Instance.Initialize(ClientId.Text))
{
 return;
}
// Login via Azure Active Directory 
if (!await MicrosoftGraphService.Instance.LoginAsync())
{
 return;
}

{% endhighlight %}

### Get the connected user's info

{% highlight csharp %}

// Retrieve user's info from Azure Active Directory
var user = await MicrosoftGraphService.Instance.User.GetProfileAsync();
UserPanel.DataContext = user;

// You can also select any fields you want in the response
MicrosoftGraphUserFields[] selectedFields = 
{
 MicrosoftGraphUserFields.Id,
 MicrosoftGraphUserFields.DisplayName,
 MicrosoftGraphUserFields.JobTitle,
 MicrosoftGraphUserFields.Mail,
 MicrosoftGraphUserFields.Department,
 MicrosoftGraphUserFields.PreferredLanguage
};

var user =await MicrosoftGraphService.Instance.User.GetProfileAsync(selectedFields);
UserPanel.DataContext = user;     

// Retrieve the user's photo 
using (IRandomAccessStream photoStream = await MicrosoftGraphService.Instance.User.GetPhotoAsync())
{
 BitmapImage photo = new BitmapImage();
 if (photoStream != null)
  {
   await photo.SetSourceAsync(photoStream);
  }
  else
  {
   photo.UriSource = new Uri("ms-appx:///SamplePages/MicrosoftGraph Service/user.png");
  }

  this.Photo.Source = photo;
}

{% endhighlight %}

### Retrieve/Send messages

{% highlight csharp %}
// Get the top 10 messages
messages = await MicrosoftGraphService.Instance.User.Message.GetEmailsAsync(10);
MessagesList.ItemsSource = messages;

// You can also select any fields you want in the response
MicrosoftGraphMessageProperties[] selectedFields = 
{ 
 MicrosoftGraphMessageProperties.Id,
 MicrosoftGraphMessageProperties.From,
 MicrosoftGraphMessageProperties.Subject,
 MicrosoftGraphMessageProperties.BodyPreview
};

messages = await MicrosoftGraphService.Instance.User.Message.GetEmailsAsync(10,selectedFields);
MessagesList.ItemsSource = messages;

// Request the next 10 messages 
messages = await MicrosoftGraphService.Instance.User.Message.NextPageEmailsAsync();
if (messages == null)
{
	// no more messages
}

// Send a message
string[] toRecipients = "user1@contoso.com;user2@contoso.com";
string subject = "This is the subject of my message;
string content = "This is the content of my message";

await MicrosoftGraphService.Instance.User.Message.SendEmailAsync(subject, content, BodyType.Text, toRecipients);

// You can also send a message in html format
string content = GetHtmlMessage();
await MicrosoftGraphService.Instance.UseR.Message.SendEmailAsync(subject, content, BodyType.Html, toRecipients);


{% endhighlight %}

### Example
[MicrosoftGraph Service Sample Page](https://github.com/Microsoft/UWPCommunityToolkit/tree/master/Microsoft.Toolkit.Uwp.SampleApp/SamplePages/MicrosoftGraph%20Service)

### Requirements (Windows 10 Device Family)

| [Device family](https://msdn.microsoft.com/windows/uwp/get-started/universal-application-platform-guide) | Universal, 10.0.10586.0 or higher |
| Namespace | Microsoft.Toolkit.Uwp.Services |

### API
* [MicrosoftGraph Service source code](https://github.com/Microsoft/UWPCommunityToolkit/tree/master/Microsoft.Toolkit.Uwp.Services/Services/MicrosoftGraph)

### NuGet Packages Required

Microsoft.Toolkit.Uwp.Services
See the [NuGet Packages](https://developer.microsoft.com/en-us/windows/uwp-community-toolkit/nugetpackages) page for complete list.