<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/128605251/17.1.3%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/T456882)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
[![](https://img.shields.io/badge/💬_Leave_Feedback-feecdd?style=flat-square)](#does-this-example-address-your-development-requirementsobjectives)
<!-- default badges end -->
<!-- default file list -->
*Files to look at*:

* [MainWindow.xaml](./CS/WpfReportDesigner_CustomizeWizard/MainWindow.xaml) (VB: [MainWindow.xaml](./VB/WpfReportDesigner_CustomizeWizard/MainWindow.xaml))
* **[MyWizardCustomizationService.cs](./CS/WpfReportDesigner_CustomizeWizard/MyWizardCustomizationService.cs) (VB: [MyWizardCustomizationService.vb](./VB/WpfReportDesigner_CustomizeWizard/MyWizardCustomizationService.vb))**
<!-- default file list end -->
# WPF Report Designer - How to customize the list of data providers in the Data Source Wizard


<p>This example illustrates how to customize the list of data providers displayed on the <a href="https://documentation.devexpress.com/#XtraReports/CustomDocument114853">Specify a Connection String</a> page of the <a href="https://documentation.devexpress.com/#XtraReports/CustomDocument115389">Data Source wizard</a> and <a href="https://documentation.devexpress.com/#XtraReports/CustomDocument115390">Report wizard</a> (e.g., to leave only the <strong>Microsoft SQL Server</strong> option), as well as make the wizard always start with this page.</p>
<p>To do this, assign an object implementing the <strong>DevExpress.Xpf.Reports.UserDesigner.IWizardCustomizationService</strong> interface to the <strong>ReportDesigner.ServicesRegistry</strong> property.<br><br><strong>See Also<br></strong><a href="https://www.devexpress.com/Support/Center/p/T600080">WPF Report Designer - How to register a custom page in the Report Wizard</a></p>

<br/>


<!-- feedback -->
## Does This Example Address Your Development Requirements/Objectives?

[<img src="https://www.devexpress.com/support/examples/i/yes-button.svg"/>](https://www.devexpress.com/support/examples/survey.xml?utm_source=github&utm_campaign=reporting-wpf-designer-data-provider-list&~~~was_helpful=yes) [<img src="https://www.devexpress.com/support/examples/i/no-button.svg"/>](https://www.devexpress.com/support/examples/survey.xml?utm_source=github&utm_campaign=reporting-wpf-designer-data-provider-list&~~~was_helpful=no)

(you will be redirected to DevExpress.com to submit your response)
<!-- feedback end -->
