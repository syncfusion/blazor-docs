---
title: "Tabs Localization"
component: "Tabs"
description: "Tabs localization section explains how to localize the tabs based on culture and set close button's tooltip text."
---

# Localization

Localization library allows to localize the default text content of
Tab. In Tab, The close button's tooltip text alone will be localize based on culture.

| Locale key | en-US (default) |
|------|------|
| closeButtonTitle | Close |

Add below code block into the `locale.json` file to define `locale` culture. For example, the below code shows adding the Arabic culture locale(`ar-AR`)

```charp
{
  "ar-AR": {
    "tab": { "closeButtonTitle": "إغلاق زر العنوان" }
  }
}
```

> Add `locale.json` file  into `wwwroot` folder and specify the path in OnAfterRender() Method.

```csharp
@using Syncfusion.Blazor
@using Syncfusion.Blazor.Navigations
@using Microsoft.JSInterop;

<SfTab ShowCloseButton="true">
    <TabItems>
        <TabItem Content="Twitter is an online social networking service that enables users to send and read short 140-charactermessages called tweets.Registered users can read and post tweets, but those who are unregistered can only readthem.Users access Twitter through the website interface, SMS or mobile device app Twitter Inc. is based in SanFrancisco and has more than 25 offices around the world.Twitter was created in March 2006 by Jack Dorsey,Evan Williams, Biz Stone, and Noah Glass and launched in July 2006. The service rapidly gained worldwide popularity,with more than 100 million users posting 340 million tweets a day in 2012.The service also handled 1.6 billionsearch queries per day.">
          <ChildContent>
                <TabHeader Text="Twitter">
                </TabHeader>
            </ChildContent>
        </TabItem>
        <TabItem Content="Facebook is an online social networking service headquartered in Menlo Park, California. Its website waslaunched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students EduardoSaverin, Andrew McCollum, Dustin Moskovitz and Chris Hughes.">
          <ChildContent>
                <TabHeader Text="Facebook">
                </TabHeader>
            </ChildContent>
        </TabItem>
        <TabItem Content="WhatsApp Messenger is a proprietary cross-platform instant messaging client for smartphones that operatesunder a subscription business model.It uses the Internet to send text messages, images, video, user location andaudio media messages to other users using standard cellular mobile numbers. As of February 2016, WhatsApp had a userbase of up to one billion,[10] making it the most globally popular messaging application.WhatsApp Inc., based inMountain View, California, was acquired by Facebook Inc.on February 19, 2014, for approximately US$19.3 billion.">
          <ChildContent>
                <TabHeader Text="Whatsapp">
                </TabHeader>
            </ChildContent>
        </TabItem>
    </TabItems>
</SfTab>

@code {
    [Inject]
    protected IJSRuntime JsRuntime { get; set; }
    protected override void OnAfterRender(bool firstRender)
    {
        this.JsRuntime.Sf().LoadLocaleData("wwwroot/locale.json").SetCulture("ar-AR");
    }
}
```

Output be like the below.

![Alt text](./images/localization.png)
