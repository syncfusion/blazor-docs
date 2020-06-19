---
title: "animations"
component: "Accordion"
description: "This example demonstrates how to set custom animation for expand and collapse actions in the Blazor Accordion component."
---

# Animations

Accordion supports custom animations for both expand and collapse actions from the provided animation option of `Animation` library.  The animation property also allows you to set [`Easing`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.AccordionActionSettingsModel~Easing.html), [`Duration`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.AccordionActionSettingsModel~Duration.html), and various other effects of your choice.

Default animation is given as `SlideDown` for expanding the panel using [`Expand`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.AccordionAnimationSettings~Expand.html) animation property and `SlideUp` for collapsing the panel using [`Collapse`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.AccordionAnimationSettings~Collapse.html) animation property. You can also disable the animation by setting animation [`Effect`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.AccordionActionSettingsModel~Effect.html) as `None`.

The sample demonstrates some types of animation that suits for Accordion. You can check all the animation effects here

```csharp
@using Syncfusion.Blazor.Navigations
@using Syncfusion.Blazor.DropDowns

<div id="container">
    <div id="default" style="padding-bottom:75px;">
        <div class="row">
            <div class="col-xs-6 col-sm-6 col-lg-6 col-md-6">
                <label> Expand Animation </label>
            </div>
            <div class="col-xs-6 col-sm-6 col-lg-6 col-md-6">
                <SfDropDownList TValue="string" Index="0" PopupHeight="150px" Placeholder="Select a animate type" TItem="AnimationEffect" DataSource="@AnimationData">
                    <DropDownListEvents ValueChange="ExpandOption" TValue="string"></DropDownListEvents>
                    <DropDownListFieldSettings Value="Text"></DropDownListFieldSettings>
                </SfDropDownList>
            </div>
        </div>
        <div class="row">
            <div class="col-xs-6 col-sm-6 col-lg-6 col-md-6">
                <label> Collapse Animation </label>
            </div>
            <div class="col-xs-6 col-sm-6 col-lg-6 col-md-6">
                <SfDropDownList TValue="string" Index="1" PopupHeight="150px" Placeholder="Select a animate type" TItem="AnimationEffect" DataSource="@AnimationData">
                    <DropDownListEvents ValueChange="CollapseOption" TValue="string"></DropDownListEvents>
                    <DropDownListFieldSettings Value="Text"></DropDownListFieldSettings>
                </SfDropDownList>
            </div>
        </div>
    </div>
    <SfAccordion>
        <AccordionAnimationSettings>
            <AccordionAnimationCollapse Effect="@CollapseEffect"></AccordionAnimationCollapse>
            <AccordionAnimationExpand Effect="@ExpandEffect"></AccordionAnimationExpand>
        </AccordionAnimationSettings>
        <AccordionItems>
            <AccordionItem Header="ASP.NET" Content="Microsoft ASP.NET is a set of technologies in the Microsoft .NET Framework for building Web applications and XML Web services. ASP.NET pages execute on the server and generate markup such as HTML, WML, or XML that is sent to a desktop or mobile browser. ASP.NET pages use a compiled,event-driven programming model that improves performance and enables the separation of application logic and user interface.">
            </AccordionItem>
            <AccordionItem Header="ASP.NET MVC" Content="The Model-View-Controller (MVC) architectural pattern separates an application into three main components: the model, the view, and the controller. The ASP.NET MVC framework provides an alternative to the ASP.NET Web Forms pattern for creating Web applications. The ASP.NET MVC framework is a lightweight, highly testable presentation framework that (as with Web Forms-based applications) is integrated with existing ASP.NET features, such as master pages and membership-based authentication.">
            </AccordionItem>
            <AccordionItem Header="JavaScript" Content="JavaScript (JS) is an interpreted computer programming language.It was originally implemented as part of web browsers so that client-side scripts could interact with the user, control the browser, communicate asynchronously, and alter the document content that was displayed.More recently, however, it has become common in both Animation development and the creation of desktop applications.">
            </AccordionItem>
        </AccordionItems>
    </SfAccordion>
</div>

@code{
    public string ExpandEffect { get; set; }
    public string CollapseEffect { get; set; }
    public void ExpandOption(Syncfusion.Blazor.DropDowns.ChangeEventArgs<string> args)
    {
        ExpandEffect = args.Value as string;
    }
    public void CollapseOption(Syncfusion.Blazor.DropDowns.ChangeEventArgs<string> args)
    {
        CollapseEffect = args.Value as string;
    }
    List<AnimationEffect> AnimationData = new List<AnimationEffect>
    {
        new AnimationEffect() { ID= "Animation1", Text= "SlideDown" },
        new AnimationEffect() { ID= "Animation2", Text= "SlideUp" },
        new AnimationEffect() { ID= "Animation3", Text= "FadeIn" },
        new AnimationEffect() { ID= "Animation4", Text= "FadeOut" },
        new AnimationEffect() { ID= "Animation5", Text= "FadeZoomIn" },
        new AnimationEffect() { ID= "Animation6", Text= "FadeZoomOut" },
        new AnimationEffect() { ID= "Animation7", Text= "ZoomIn" },
        new AnimationEffect() { ID= "Animation8", Text= "ZoomOut"},
        new AnimationEffect() { ID= "Animation9", Text= "None" }
    };
    public class AnimationEffect
    {
        public string ID { get; set; }
        public string Text { get; set; }
    }
}
```

Output be like the below.

![Customize Accordion expand or collapse animation behavior](./images/animation.png)
