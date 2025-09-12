<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/128605251/23.1.4%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/T456882)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
[![](https://img.shields.io/badge/💬_Leave_Feedback-feecdd?style=flat-square)](#does-this-example-address-your-development-requirementsobjectives)
<!-- default badges end -->
# Reporting for WPF - How to customize the list of data providers in the Data Source Wizard

This example illustrates how to customize the list of data providers displayed on the **Specify a Connection String** page of the [Data Source Wizard](https://docs.devexpress.com/XtraReports/400461/desktop-reporting/wpf-reporting/end-user-report-designer-for-wpf/gui/data-source-wizard) and [Report Wizard](https://docs.devexpress.com/XtraReports/114841/desktop-reporting/wpf-reporting/end-user-report-designer-for-wpf/gui/report-wizard) (e.g., to leave only the **Microsoft SQL Server** option), as well as make the wizard always start with this page.
To do this, assign an object implementing the [IWizardCustomizationService](https://docs.devexpress.com/WPF/DevExpress.Xpf.Reports.UserDesigner.ReportWizard.IWizardCustomizationService) interface to the [ReportDesigner.ServicesRegistry](https://docs.devexpress.com/WPF/DevExpress.Xpf.Reports.UserDesigner.ReportDesignerBase.ServicesRegistry) property.

## Files to Review
* [MainWindow.xaml](./CS/WpfReportDesigner_CustomizeWizard/MainWindow.xaml) (VB: [MainWindow.xaml](./VB/WpfReportDesigner_CustomizeWizard/MainWindow.xaml))
* [MyWizardCustomizationService.cs](./CS/WpfReportDesigner_CustomizeWizard/MyWizardCustomizationService.cs) (VB: [MyWizardCustomizationService.vb](./VB/WpfReportDesigner_CustomizeWizard/MyWizardCustomizationService.vb))

## More Examples

* [WPF Report Designer - How to register a custom page in the Report Wizard](https://github.com/DevExpress-Examples/reporting-wpf-wizard-custom-page)
<!-- feedback -->
## Does this example address your development requirements/objectives?

[<img src="https://www.devexpress.com/support/examples/i/yes-button.svg"/>](https://www.devexpress.com/support/examples/survey.xml?utm_source=github&utm_campaign=reporting-wpf-designer-data-provider-list&~~~was_helpful=yes) [<img src="https://www.devexpress.com/support/examples/i/no-button.svg"/>](https://www.devexpress.com/support/examples/survey.xml?utm_source=github&utm_campaign=reporting-wpf-designer-data-provider-list&~~~was_helpful=no)

(you will be redirected to DevExpress.com to submit your response)
<!-- feedback end -->
