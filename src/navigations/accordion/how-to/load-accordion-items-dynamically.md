---
title: "Load accordion items dynamically"
component: "Accordion"
description: "This example demonstrates how to dynamically load or add an accordion item in the Blazor Accordion component."
---

# Load items dynamically

Accordion items can be added dynamically by passing the item through [`AddItem`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.SfAccordion~AddItem.html) method.

In the following demo, new items are added dynamically when you click **Add Item** button.

```csharp
@using Syncfusion.Blazor.Navigations
@using Syncfusion.Blazor.Buttons

<SfButton @onclick="AddItemClick" Content="ADD Item"></SfButton>
<br/>
<SfAccordion @ref="@Accordion">
    <AccordionItems>
        <AccordionItem Expanded="true" Header="ASP.NET" Content="Microsoft ASP.NET is a set of technologies in the Microsoft .NET Framework for building Web applications and XML Web services. ASP.NET pages execute on the server and generate markup such as HTML, WML, or XML that is sent to a desktop or mobile browser. ASP.NET pages use a compiled,event-driven programming model that improves performance and enables the separation of application logic and user interface."></AccordionItem>
        <AccordionItem Header="ASP.NET MVC" Content="The Model-View-Controller (MVC) architectural pattern separates an application into three main components: the model, the view, and the controller. The ASP.NET MVC framework provides an alternative to the ASP.NET Web Forms pattern for creating Web applications. The ASP.NET MVC framework is a lightweight, highly testable presentation framework that (as with Web Forms-based applications) is integrated with existing ASP.NET features, such as master pages and membership-based authentication."></AccordionItem>
        <AccordionItem Header="JavaScript" Content="JavaScript (JS) is an interpreted computer programming language.It was originally implemented as part of web browsers so that client-side scripts could interact with the user, control the browser, communicate asynchronously, and alter the document content that was displayed.More recently, however, it has become common in both game development and the creation of desktop applications."></AccordionItem>
    </AccordionItems>
</SfAccordion>

@code{
    SfAccordion Accordion;
    public void AddItemClick()
    {
        Accordion.AddItem(new AccordionItem { Header = "ASP.NET Razor", Content = "Razor is an ASP.NET programming syntax used to create dynamic web pages with the C# or Visual Basic .NET programming languages. Razor was in development in June 2010 and was released for Microsoft Visual Studio 2010 in January 2011. Razor is a simple-syntax view engine and was released as part of MVC 3 and the WebMatrix tool set. Side Code content" }, 2);
    }
}
```

Output be like the below.

![Dynamic AccordionItems](../images/dynamicAccordion.png)
