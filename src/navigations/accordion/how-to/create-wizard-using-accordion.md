# Create wizard

Accordion items can be disabled and expanded dynamically using accordion item **Disabled** and **Expanded** property.

In the below demo, designed for simple payment module that Enable/Disable Accordion based on sequential validation of each Accordion content.

```csharp
@using Syncfusion.Blazor.Navigations
@using Syncfusion.Blazor.Inputs
@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.Calendars
@using Syncfusion.Blazor.Popups

<div class='template_title'> Online Shopping Payment Module</div>
<SfAccordion ID="AccordionElement" @ref="@Accordion">
    <AccordionEvents Created="OnCreate"></AccordionEvents>
    <AccordionItems>
        <AccordionItem Disabled=@DisableSignInItem @bind-Expanded="ExpandSignInItem">
            <HeaderTemplate>Sign In</HeaderTemplate>
            <ContentTemplate>
                <div id="Sign_In_Form" style="padding:10px">
                    <form id="formId">
                        <div class="form-group">
                            <div class="e-float-input">
                                <SfTextBox @ref="@EmailTextbox" Placeholder="Email"></SfTextBox>
                            </div>
                            <div class="e-float-input">
                                <SfTextBox @ref="@PasswordTextbox" Placeholder="Password" Type="InputType.Password"></SfTextBox>
                            </div>
                        </div>
                    </form>
                    <div style="text-align: center">
                        <SfButton @onclick="@OnSignIn">Continue</SfButton>
                        @if (EmptyField)
                        {
                            <div class="Error">* Please fill all fields</div>
                        }
                    </div>
                </div>
            </ContentTemplate>
        </AccordionItem>
        <AccordionItem Disabled=@DisableDeliveryItem @bind-Expanded="ExpandDeliveryItem">
            <HeaderTemplate>Delivery Address</HeaderTemplate>
            <ContentTemplate>
                <div>
                    <div id="Address_Fill" style="padding:10px">
                        <form id="formId_Address">
                            <div class="form-group">
                                <div class="e-float-input">
                                    <SfTextBox @ref="@NameTextbox" Placeholder="Name"></SfTextBox>
                                </div>
                            </div>
                            <div class="form-group">
                                <div class="e-float-input">
                                    <SfTextBox @ref="@AddressTextbox" Placeholder="Address"></SfTextBox>
                                </div>
                            </div>
                            <div class="form-group">
                                <SfNumericTextBox TValue="int" @ref="@MobileNumberTextbox" Placeholder="Mobile" FloatLabelType="@FloatLabelType.Auto" ShowSpinButton="false" Format="0"></SfNumericTextBox>
                            </div>
                        </form>
                        <div style="text-align: center">
                            <SfButton @onclick="@OnContinue">Continue</SfButton>
                            @if (EmptyField)
                            {
                                <div class="Error">* Please fill all fields</div>
                            }
                        </div>
                    </div>
                </div>
            </ContentTemplate>
        </AccordionItem>
        <AccordionItem Disabled=@DisableCardItem @bind-Expanded="ExpandCardItem">
            <HeaderTemplate> Card Details</HeaderTemplate>
            <ContentTemplate>
                <div id="Card_Fill" style="padding:10px">
                    <div class="col-xs-6 col-sm-6 col-lg-6 col-md-6">
                        <div class="form-group">
                            <SfNumericTextBox TValue="int" @ref="@CardNumberTextbox" Placeholder="Card No" FloatLabelType="@FloatLabelType.Auto" ShowSpinButton="false" Format="0"></SfNumericTextBox>
                        </div>
                    </div>
                    <div class="col-xs-6 col-sm-6 col-lg-6 col-md-6">
                        <div class="form-group">
                            <div class="e-float-input">
                                <SfTextBox @ref="@CardHolderNameTextbox" Placeholder="CardHolder Name"></SfTextBox>
                            </div>
                        </div>
                    </div>
                    <div class="col-xs-6 col-sm-6 col-lg-6 col-md-6">
                        <SfDatePicker TValue="DateTime" Width="100%" Placeholder="Expiry Date" Format="MM-yyyy" Readonly="false"></SfDatePicker>
                    </div>
                    <div class="col-xs-6 col-sm-6 col-lg-6 col-md-6">
                        <div class="form-group">
                            <SfNumericTextBox @ref="@CvvTextbox" TValue="int" Placeholder="CVV" FloatLabelType=@FloatLabelType.Auto Format="0" ShowSpinButton="false"></SfNumericTextBox>
                        </div>
                    </div>
                </div>
                <div style="text-align: center">
                    <SfButton @onclick="@GoBack">Back</SfButton>
                    <SfButton @onclick="@SaveDetails">Save</SfButton>
                    @if (EmptyField)
                    {
                        <div class="Error">* Please fill all fields</div>
                    }
                </div>
            </ContentTemplate>
        </AccordionItem>
    </AccordionItems>
</SfAccordion>

<SfDialog @ref="AlertDialog" Width=250 Target="#AccordionElement" IsModal=true Visible=false ShowCloseIcon="true">
    <DialogEvents Created="DialogCreate"></DialogEvents>
    <DialogTemplates>
        <Header><div>Alert</div></Header>
        <Content><div>Your payment successfully processed</div></Content>
    </DialogTemplates>
    <DialogButtons>
        <DialogButton OnClick="@OnSubmit" Content="OK" IsPrimary="true"></DialogButton>
    </DialogButtons>
</SfDialog>

@code{
    SfAccordion Accordion;
    SfTextBox EmailTextbox;
    SfTextBox PasswordTextbox;
    SfTextBox NameTextbox;
    SfTextBox AddressTextbox;
    SfDialog AlertDialog;
    SfTextBox CardHolderNameTextbox;
    public SfNumericTextBox<int> CardNumberTextbox { get; set; }
    public SfNumericTextBox<int> MobileNumberTextbox { get; set; }
    public SfNumericTextBox<int> CvvTextbox { get; set; }
    public Boolean EmptyField { get; set; } = false;
    public Boolean DisableSignInItem { get; set; }
    public Boolean DisableDeliveryItem { get; set; }
    public Boolean DisableCardItem { get; set; }
    public Boolean ExpandSignInItem { get; set; }
    public Boolean ExpandDeliveryItem { get; set; }
    public Boolean ExpandCardItem { get; set; }

    public void OnCreate()
    {
        DisableDeliveryItem = true;
        DisableCardItem = true;
    }

    public void OnSignIn()
    {
        if (EmailTextbox.Value == null || PasswordTextbox.Value == null)
        {
            EmptyField = true;
        }
        else
        {
            EmptyField = false;
            DisableDeliveryItem = false;
            Accordion.Select(1);
            ExpandSignInItem = false;
            ExpandDeliveryItem = true;
        }
    }
    public void OnContinue()
    {
        if (NameTextbox.Value == null || AddressTextbox.Value == null || MobileNumberTextbox == null)
        {
            EmptyField = true;
        }
        else
        {
            DisableCardItem = false;
            Accordion.Select(2);
            ExpandDeliveryItem = false;
            ExpandCardItem = true;
        }
    }
    public void GoBack()
    {
        Accordion.Select(1);
        ExpandCardItem = false;
        ExpandDeliveryItem = true;
    }
    public void SaveDetails()
    {
        if (CardNumberTextbox == null || CardHolderNameTextbox == null || CvvTextbox == null)
        {
            EmptyField = true;
        }
        else
        {
            EmptyField = false;
            AlertDialog.Show();
        }
    }
    public void DialogCreate()
    {
        AlertDialog.Hide();
    }
    public void OnSubmit(Object args)
    {

        AlertDialog.Hide();
        ExpandCardItem = false;
        DisableSignInItem = false;
        DisableDeliveryItem = true;
        DisableCardItem = true;
        Accordion.Select(0);
    }
}

<style>
    .Error {
        color: red;
    }
</style>
```

Output be like the below.

![Accordion wizard](../images/wizard.png)