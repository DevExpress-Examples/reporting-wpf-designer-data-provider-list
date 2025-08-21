<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/128605251/25.1.4%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/T456882)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
[![](https://img.shields.io/badge/💬_Leave_Feedback-feecdd?style=flat-square)](#does-this-example-address-your-development-requirementsobjectives)
<!-- default badges end -->
# Reporting for WPF - Customize the Data Providers List in the Data Source Wizard

The following example customizes the [Report Wizard](https://docs.devexpress.devx/XtraReports/114841/desktop-reporting/wpf-reporting/end-user-report-designer-for-wpf/gui/report-wizard) and [Data Source Wizard](https://docs.devexpress.devx/XtraReports/400461/desktop-reporting/wpf-reporting/end-user-report-designer-for-wpf/gui/data-source-wizard0) pages. Both wizards display "Select a Data Connection Type" (`ChooseDataProviderPage`) as the start page. The list of available SQL data source providers is limited to MSSQLServer, Oracle, Amazon Redshift, MySQL, Postgres, and SQLite. 

![](/images/custom-page.png)

## Implementation Details

The `WizardCustomizationService` class implements the [IWizardCustomizationService](https://docs.devexpress.com/WPF/DevExpress.Xpf.Reports.UserDesigner.ReportWizard.IWizardCustomizationService) interface and allows you to customize the Data Source and Report Wizards. The `CustomizeDataSourceWizard` and `CustomizeReportWizard` methods contain the main logic for wizard customization:

* `StartPage` - sets the wizard start page to the `ChooseDataProviderPage`.
* `ReportType` - specifies the report type in the report model.
* `DataSourceType` - specifies the data source type in the report model.

The `CustomizeProviders` method limits the available data source types and providers to a predefined list.

The [ReportDesigner.ServicesRegistry](https://docs.devexpress.com/WPF/DevExpress.Xpf.Reports.UserDesigner.ReportDesignerBase.ServicesRegistry) property registers the `MyWizardCustomizationService` type in XAML.


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

