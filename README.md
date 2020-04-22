# How to hide expander in Xamarin.Forms TreeView (SfTreeView)

You can hide expander of Xamarin.Forms [SfTreeView](https://help.syncfusion.com/xamarin/treeview/overview?) by setting the [ExpanderWidth](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~ExpanderWidth.html?) property to **zero** in Xamarin.Forms.

You can also refer the following article.

https://www.syncfusion.com/kb/11422/how-to-hide-expander-in-xamarin-forms-treeview-sftreeview

**XAML**

Set the [ExpandActionTarget](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~ExpandActionTarget.html?) to **Node** to expand or collapse the [TreeViewNode](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.TreeView.Engine.TreeViewNode.html?).
``` xml
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TreeViewXamarin"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.TreeView;assembly=Syncfusion.SfTreeView.XForms"
             x:Class="TreeViewXamarin.MainPage">
 
    <ContentPage.BindingContext>
        <local:FileManagerViewModel x:Name="viewModel"/>
    </ContentPage.BindingContext>
 
    <StackLayout>
        <syncfusion:SfTreeView x:Name="treeView" ExpanderWidth="0" ExpandActionTarget="Node" ChildPropertyName="SubFiles" ItemTemplateContextType="Node" ItemsSource="{Binding ImageNodeInfo}">
            <syncfusion:SfTreeView.ItemTemplate>
                <DataTemplate>
                    <Grid x:Name="grid" RowSpacing="0" >
                        <Grid.ColumnDefinitions>
                            <ColumnDefinition Width="40" />
                            <ColumnDefinition Width="*" />
                        </Grid.ColumnDefinitions>
                        <Image Source="{Binding Content.ImageIcon}" VerticalOptions="Center" HorizontalOptions="Center" HeightRequest="35" WidthRequest="35"/>
                        <Grid Grid.Column="1" RowSpacing="1" Padding="1,0,0,0" VerticalOptions="Center">
                            <Label LineBreakMode="NoWrap" Text="{Binding Content.ItemName}" VerticalTextAlignment="Center"/>
                        </Grid>
                    </Grid>
                </DataTemplate>
            </syncfusion:SfTreeView.ItemTemplate>
        </syncfusion:SfTreeView>
    </StackLayout>
</ContentPage>
```
**Output**

![HideTreeViweNode](https://github.com/SyncfusionExamples/hide-expander-treeview-xamarin/blob/master/ScreenShot/HideTreeViewNode.gif)
