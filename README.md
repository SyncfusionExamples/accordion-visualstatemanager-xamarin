# How to customize the appearance of  Accordion using VisualStateManager in Xamarin.Forms (SfAccordion)

You can customize the appearance of [SfAccordion](https://help.syncfusion.com/xamarin/accordion/getting-started?) using [VisualStateManager](https://help.syncfusion.com/xamarin/accordion/appearance?_ga=2.36226467.244544536.1588564846-1204678185.1570168583#visual-state-manager) in Xamarin.Forms.

You can also refer the following article.

https://www.syncfusion.com/kb/11497/how-to-customize-the-appearance-of-accordion-using-visualstatemanager-in-xamarin-forms

**XAML**

Defining the **VisualStates** to customize **Accordion** appearance.
``` xml
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Accordion;assembly=Syncfusion.Expander.XForms"
             x:Class="AccordionXamarin.MainPage" Padding="{OnPlatform iOS='0,40,0,0'}">
 
    <ContentPage.Content>
        <syncfusion:SfAccordion x:Name="Accordion" ExpandMode="SingleOrNone" BindableLayout.ItemsSource="{Binding Info}">
            <BindableLayout.ItemTemplate>
                <DataTemplate>
                    <syncfusion:AccordionItem x:Name="AccordionItem">
                        <syncfusion:AccordionItem.Header>
                            <Grid HeightRequest="50" Padding="10,0">
                                <Label Text="{Binding Name}" VerticalOptions="Center" HorizontalOptions="StartAndExpand"/>
                            </Grid>
                        </syncfusion:AccordionItem.Header>
                        <syncfusion:AccordionItem.Content>
                            <Grid BackgroundColor="NavajoWhite" Padding="10">
                                <Label Text="{Binding Description}"/>
                            </Grid>
                        </syncfusion:AccordionItem.Content>
                        <VisualStateManager.VisualStateGroups>
                            <VisualStateGroupList>
                                <VisualStateGroup>
                                    <VisualState Name="Expanded">
                                        <VisualState.Setters>
                                            <Setter Property="HeaderBackgroundColor" Value="LightPink"/>
                                            <Setter Property="IconColor" Value="Red"/>
                                        </VisualState.Setters>
                                    </VisualState>
                                    <VisualState Name="Collapsed">
                                        <VisualState.Setters>
                                            <Setter Property="HeaderBackgroundColor" Value="LightGreen"/>
                                            <Setter Property="IconColor" Value="Blue"/>
                                        </VisualState.Setters>
                                    </VisualState>
                                </VisualStateGroup>
                            </VisualStateGroupList>
                        </VisualStateManager.VisualStateGroups>
                    </syncfusion:AccordionItem>
                </DataTemplate>
            </BindableLayout.ItemTemplate>
        </syncfusion:SfAccordion>
    </ContentPage.Content>
</ContentPage>
```
**Output**

![VisualStateManagerAccordion](https://github.com/SyncfusionExamples/accordion-visualstatemanager-xamarin/blob/master/ScreenShots/VisualStateManagerAccordion.gif)
