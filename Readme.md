<!-- default badges list -->
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/T456882)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
[![](https://img.shields.io/badge/💬_Leave_Feedback-feecdd?style=flat-square)](#does-this-example-address-your-development-requirementsobjectives)
<!-- default badges end -->
# Reporting for WPF - Customize the Data Providers List in the Data Source Wizard

The example customizes [Report Wizard](http://docs.devexpress.com/XtraReports/114841/desktop-reporting/wpf-reporting/end-user-report-designer-for-wpf/gui/report-wizard) and [Data Source Wizard](http://docs.devexpress.com/XtraReports/400461/desktop-reporting/wpf-reporting/end-user-report-designer-for-wpf/gui/data-source-wizard) to achieve the following:

- Display `ChooseDataProviderPage` ("Select a Data Connection Type") as the start page.
- Restrict available SQL data source providers to MSSQLServer, Oracle, Amazon Redshift, MySQL, Postgres, and SQLite.

![](/images/custom-page.png)

## Implementation Details

### Customization Service

To customize Data Source and Report Wizards, create a customization service (`MyWizardCustomizationService` in this example) that implements the [IWizardCustomizationService](https://docs.devexpress.com/WPF/DevExpress.Xpf.Reports.UserDesigner.ReportWizard.IWizardCustomizationService) interface.  

`CustomizeDataSourceWizard` and `CustomizeReportWizard` methods contain main logic for wizard customization:

* `StartPage` - sets the wizard start page to `ChooseDataProviderPage` ("Select a Data Connection Type").
* `ReportType` - specifies the report type in the report model.
* `DataSourceType` - specifies the data source type in the report model.

The `CustomizeProviders` method limits available data source types and providers to a predefined list.

```cs
    // ...
    // Сustomization service for the Data Source and Report wizards.
    public class MyWizardCustomizationService : IWizardCustomizationService {

        static readonly string[] allowedSqlDataSourceProviders = new[] {
            "MSSqlServer", "Oracle", "Amazon Redshift", "MySql", "Postgres", "SQLite"
        };
        // Modifies the Data Source wizard's start page and data source type. 
        void IDataSourceWizardCustomizationService.CustomizeDataSourceWizard(DataSourceWizardCustomizationModel customization, ViewModelSourceIntegrityContainer container) {
            if(customization.StartPage == typeof(ChooseExistingConnectionPage<IDataSourceModel>)) {
                customization.Model.DataSourceType = DataSourceType.Xpo;
                customization.StartPage = typeof(ChooseDataProviderPage<IDataSourceModel>);
            }
            CustomizeProviders(container);
        }
        // Modifies the Report wizard's start page, data source type, and report type.
        void IWizardCustomizationService.CustomizeReportWizard(ReportWizardCustomizationModel customization, ViewModelSourceIntegrityContainer container) {
            if (customization.StartPage == typeof(ChooseReportTypePage<XtraReportModel>)) {
                customization.Model.ReportType = ReportType.Standard;
                customization.Model.DataSourceType = DataSourceType.Xpo;
                customization.StartPage = typeof(ChooseDataProviderPage<XtraReportModel>);
            }
            CustomizeProviders(container);
        }
        // ...
        // Filters available SQL data source providers and registers allowed providers in the container.
        static void CustomizeProviders(IntegrityContainer container) {
            var providers = container.Resolve<List<ProviderLookupItem>>();
            providers.RemoveAll(x => !allowedSqlDataSourceProviders.Contains(x.ProviderKey));
            container.RegisterInstance<DataSourceTypes>(new DataSourceTypes(WizardDataSourceType.Sql));

        }
    }
}
```

### Service Registration

The [ReportDesigner.ServicesRegistry](https://docs.devexpress.com/WPF/DevExpress.Xpf.Reports.UserDesigner.ReportDesignerBase.ServicesRegistry) property registers the `MyWizardCustomizationService` type in XAML and applies customization logic.

```xaml
<dxrud:ReportDesigner x:Name="reportDesigner">
    <dxrud:ReportDesigner.ServicesRegistry>
        <dxda:TypeEntry ServiceType="{x:Type dxrudw:IWizardCustomizationService}" ConcreteType="{x:Type local:MyWizardCustomizationService}" />
    </dxrud:ReportDesigner.ServicesRegistry>
</dxrud:ReportDesigner>
```
## Files to Review

* [MainWindow.xaml](./CS/WpfReportDesigner_CustomizeWizard/MainWindow.xaml) (VB: [MainWindow.xaml](./VB/WpfReportDesigner_CustomizeWizard/MainWindow.xaml))
* [MyWizardCustomizationService.cs](./CS/WpfReportDesigner_CustomizeWizard/MyWizardCustomizationService.cs) (VB: [MyWizardCustomizationService.vb](./VB/WpfReportDesigner_CustomizeWizard/MyWizardCustomizationService.vb))

## Documentation

* [Report Wizard](https://docs.devexpress.com/XtraReports/114841/desktop-reporting/wpf-reporting/end-user-report-designer-for-wpf/gui/report-wizard)
* [Data Source Wizard](https://docs.devexpress.com/XtraReports/400461/desktop-reporting/wpf-reporting/end-user-report-designer-for-wpf/gui/data-source-wizard)

## More Examples

* [WPF Report Designer - How to register a custom page in the Report Wizard](https://github.com/DevExpress-Examples/reporting-wpf-wizard-custom-page)
<!-- feedback -->
## Does this example address your development requirements/objectives?

[<img src="https://www.devexpress.com/support/examples/i/yes-button.svg"/>](https://www.devexpress.com/support/examples/survey.xml?utm_source=github&utm_campaign=reporting-wpf-designer-data-provider-list&~~~was_helpful=yes) [<img src="https://www.devexpress.com/support/examples/i/no-button.svg"/>](https://www.devexpress.com/support/examples/survey.xml?utm_source=github&utm_campaign=reporting-wpf-designer-data-provider-list&~~~was_helpful=no)

(you will be redirected to DevExpress.com to submit your response)
<!-- feedback end -->





