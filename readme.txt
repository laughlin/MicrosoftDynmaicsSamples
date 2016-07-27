Microsoft Dynamics CRM 2016 SDK
Sample Code Readme

Overview
This document gives you information about how to build and run the samples included in this SDK. Typically, you open the sample’s solution or project file in Microsoft Visual Studio 2012 or later and press F5 to run a sample. 
The samples work with all supported Microsoft Dynamics CRM deployments. All samples use the helper code in the SampleCode\CS\HelperCode or SampleCode\VB\HelperCode folders to handle connecting to and authenticating with the Microsoft Dynamics CRM server.
In that same helper code folder is a file named MyOrganizationCrmSdkTypes. This file contains the early-bound entity types, for example, Account and Contact, and was generated using the CrmSvcUtil.exe program located in the SDK\Bin folder. The file is included (linked) in all Visual Studio projects that use early-bound entity types and will help you start coding. You can generate and use your own early-bound types file in your projects at any time.

Instructions
The following instructions apply to most of the SDK samples. If a sample’s folder contains a Readme file, follow the instructions provided in that file.

To build and run a sample, follow these steps:
1.	Double-click the sample’s solution (.sln) file in Windows Explorer to open the sample’s project in Visual Studio. If a solution file does not exist, double-click the sample’s project (.csproj or .vbproj) file instead.
2.	Open the project’s properties by right-clicking the project in Solution Explorer and selecting Properties.
3.	If there is more than one sample class in the project, you must choose which one will be executed. Select a sample class to execute from the Startup object drop-down list.
4.	Press F5 to build and run the sample or select Build Solution in the Build menu to build it.
5.	Enter the following information at the prompts:

Prompt 	Description 
Enter a CRM server name and port [crm.dynamics.com]	Type the name of your Microsoft Dynamics CRM server. The default is crm.dynamics.com.
Example: myservername  (on-premises)
Example: myservername:5500 (on-premises)
Example: crm.dynamics.com  (online)
Example: crm4.dynamics.com  (online)
Example: dev.myservername.com (IFD)
Is this server configured for Secure Socket Layer (https) (y/n) [n] 	Type y if the URL you use to access Microsoft Dynamics CRM 2016 begins with https://, otherwise default is n.
Is this organization provisioned in Microsoft Office 365 (y/n) [n]	Type y if this is an Microsoft Online Services (MOS) provisioned organization, otherwise default is n.
Enter domain\username	For Microsoft Dynamics CRM 2016 on-premises, type your network domain and user name separated by a backslash (\).
Example: mydomain\tadams

For Microsoft Dynamics CRM Online, type your Microsoft account or Microsoft Online Services username.
Example: terryadams@live.com
Example: terryadams@xxx.onmicrosoft.com

If you just press <Enter> for the username, the program will attempt to use your saved credentials. If there are none, it will fail.
Enter password	Type your password. 
Specify an organization number (1-n) [1]	From the list of organizations shown that you belong to, type the corresponding number. The default is 1, indicating the first organization in the list.
Do you want these entity records deleted? (y/n) [y]	Type y for yes and n for no. The default is y. After the program runs, you can choose to delete any records that were created, or you can leave them to view in the Web application or Microsoft Dynamics CRM for Microsoft Office Outlook.
Press Enter to exit	Press Enter to exit the program.

After the first run of an SDK console based sample, the server, organization, and user name information you entered when prompted is saved in an XML configuration file for re-use the next time you run a sample. This feature removes the need to enter that information again as you run additional samples. After the first sample run, the console prompts are as follows. 
Prompt 	Description 
Specify the saved server configuration number (1-x) [x]: 	Enter zero (0) to create a new server configuration and follow the prompts as shown in the table above. Otherwise, enter the number of a saved configuration as shown in the displayed list.
Enter Password: 	If prompted, type your password. The characters will show as “*” in the window.
Do you want these entity records deleted? (y/n) [y] 	Type y for yes and n for no. After the program runs, demonstrating create, retrieve and update of an account record, you can choose to delete the record that was created, or you can leave it so that you can view it in the Web application or Microsoft Dynamics CRM for Microsoft Office Outlook.
Press Enter to exit 	Press Enter to exit the program.


Important Notes
•	All samples target the Microsoft .NET Framework 4.5.2, which must be installed on your development computer.
•	All samples make use of NuGet packages to obtain the CRM SDK and other assemblies. A connection to the internet is required for these packages to automatically be downloaded prior to a build. 
•	The sample files are not intended to be used in a production environment. You should deploy this sample to a test environment and examine it for interaction or interference with other parts of the system. 
•	Before you deploy this sample to a production environment, make sure that you consider the existing customizations you may have implemented in Microsoft Dynamics CRM 2016.
•	A small number of samples require additional (fictitious) system user accounts to exist on the Microsoft Dynamics CRM server other than the system user account running the sample. For more information, see the following section.
•	Samples executing on-premises that create fictitious user accounts will prompt for a Lightweight Directory Access Protocol (LDAP) path. For example, a server address of a.b.c.com would have a path value of LDAP://a/DC=b,DC=c,DC=com. 

Samples that Require Additional User Accounts
The following table lists the SDK samples that require additional fictitious system user accounts to exist, other than the system user account running the sample. The accounts must be in the target Microsoft Dynamics CRM organization.
 
Sample Code	Role
(Fictitious User)
BusinessDataModel\Goals\OverrideGoalTotalCount
GeneralProgramming\EarlyBound\SharingRecords
FieldSecurity\RetrieveSecuredFieldsForAUser	Marketing Manager
(Samantha Smith)
VisualizationsAndDashboards\AssignVisualizationToUser
VisualizationsAndDashboards\AssignDashboardToUser
GeneralProgramming\EarlyBound\BasicContextExamples
GeneralProgramming\Authentication\ImpersonateWithOnBehalfOfPrivilege
BusinessDataModel\Goals\UsingQueriesToTrackGoals
BusinessDataModel\Goals\RollupAllGoalsForCustomPeriodAgainstTargetRevenue
BusinessDataModel\Goals\RollupAllGoalsForFiscalPeriodAndStretchedTargetRevenue
BusinessDataModel\ScheduleAndAppointment\QueryScheduleOfMultipleUsers
BusinessDataModel\BusinessManagement\WorkingWithNegativePrices
SampleCode\CS\BusinessDataModel\ScheduleAndAppointment\QueryScheduleOfMultipleUsers	Sales Manager
(Kevin Cook)
BusinessDataModel\Goals\UsingQueriesToTrackGoals
BusinessDataModel\Goals\RollupAllGoalsForCustomPeriodAgainstTargetRevenue
BusinessDataModel\Goals\RollupAllGoalsForFiscalPeriodAndStretchedTargetRevenue
BusinessDataModel\BusinessManagement\WorkingWithNegativePrices	Sales Persons
(Nancy Anderson)
(David Bristol)
GeneralProgramming\EarlyBound\UserAccess	Delegate
(Dan Wilson)
(Christen Anderson)
BusinessDataModel\UsersAndRoles\AddRoleToUser
BusinessDataModel\UsersAndRoles\DisableOREnableUser
BusinessDataModel\UsersAndRoles\DoesUserBelongToRole
BusinessDataModel\UsersAndRoles\RemoveRoleFromUser
BusinessDataModel\UsersAndRoles\RetrieveAUser
	No Role
(Dan Park)
BusinessDataModel\UsersAndRoles\CreateAUser	No Role
(Darren Parker)

For Microsoft Dynamics CRM 2016 on-premises, these fictitious user accounts will be created automatically by the sample if the user that runs the sample has System Administrator privilege in Active Directory and Microsoft Dynamics CRM. For Microsoft Dynamics CRM Online, you must manually create these fictitious users in the target organization before running the sample. Alternately, you can modify the SampleCode\CS\HelperCode\SystemUserProvider.cs or SampleCode\VB\HelperCode\SystemUserProvider.vb files in the SDK download to use system user accounts that already exist in your Microsoft Dynamics CRM organization. Assign these accounts the roles indicated in the above table.

Known Issues
The following samples have known issues that prevent them from running correctly. These issues will be fixed in a future release of the SDK. 

A bug in the CrmServiceHelpers.cs and CrmServiceHelpers.vb helper code requires that when prompted for a server name in the console window, the user enters a server name of dev.serverName for an IFD server. For example: dev.contoso.com.

Change History

7.0 
•	All samples were updated to target .NET Framework 4.5.2 and support the 2015 release.
•	CRM SDK assembly references were replaced by NuGet packages.

8.0 
•	The ‘QuickStart with Simplified Connection’ sample has been updated to use Microsoft.Xrm.Tooling.Connector for authenticating with the web services. This change adds OAuth authentication support plus full run-time diagnostics of the connection process. Diagnostics are enabled using settings in the app.config file. You can find the sample in the SDK download under SampleCode\CS\QuickStart.

Copyright 
This document is provided "as-is". Information and views expressed in this document, including URL and other Internet Web site references, may change without notice. You bear the risk of using it. 

Some examples depicted herein are provided for illustration only and are fictitious. No real association or connection is intended or should be inferred. 

This document does not provide you with any legal rights to any intellectual property in any Microsoft product. You may copy and use this document for your internal, reference purposes.

© 2016 Microsoft Corporation. All rights reserved.

Microsoft, Active Directory, ActiveX, BizTalk, Excel, Great Plains, Internet Explorer, JScript, Microsoft Dynamics, MSN, Outlook, PivotTable, PivotChart, Visual Basic, Visual Studio, Windows, Windows Live, Windows Server, and Windows Vista are trademarks of the Microsoft group of companies. 

All other trademarks are property of their respective owners.

