# Getting Started {#getting-started}

<a href="../configurations" target="_self"><i id="go" class="omd_icon-go welcome-option"></i></a>

If you are a member of an organization using OMD Go, your OMD Application Manager will maintain access permissions.
Contact your IT department or OMD Application Manager directly to gain access to your organization's configuration. Once you 
have been given permission, the configuration name will appear in the <a href="../configurations" target="_configurations">Configurations</a> page. Clicking on the configuration 
will present buttons on the top right of the screen, representing the OMD modules that you have access to.

If you are a new subscriber and would like to learn more about OMD Go, you may <a href="https://www.optimizemyday.com/home/en/contact/" target="_contact">ask the OMD team</a> to create a demo configuration for you or to provide an online demonstration of the capabilities of OMD Go.

<a href="documentation.html" target="_self"><i id="go" class="omd_icon-report welcome-option"></i></a>

If you are a partner or consultant supporting your customer with the implementation of OMD Go, you have access to a number of [documents](documentation.md) describing the use and configuration of OMD. As a general starting point, read the [OMD Integration Guide](../integration/index.html). This document includes all relevant information to exchange data between your ERP system and OMD. If you wish to use a shortcut for a quick evaluation, follow the section [Import Data with Excel](./#import-excel) below.

During the setup of a development environment, you might require some information from the <a href="../configuration/index.html">OMD Configuration Guide</a>, providing you with details about the preferences that are applicable on configuration level.

Once you have uploaded your ERP data to OMD, you may want to use OMD Scheduler to access the planning. Read the <a href="../integration/assets/pdf/OMD Scheduler - User Guide.pdf" target="_scheduler_user_guide">OMD Scheduler User Guide</a> for details on how to use OMD Scheduler.

<a href="../integration/assets/pdf/Jira_Manual.pdf" target="_support_guide"><i id="go" class="omd_icon-MONITORING welcome-option"></i></a>

Finally, any issue you may want to let us know, or for follow-up on open issues, read the <a href="../integration/assets/pdf/Jira_Manual.pdf" target="_support_guide">OMD Support Guide</a> to find out how we have organized our support facilities. It is a very lively environment which we use for our internal development as well. Hence, adding a ticket to our [Support Desk system](https://crmalliance.atlassian.net/login) will most likely have a faster response than sending e-mails to individual OMD staff. If you do not have access to our Help Desk system, please contact your OMD Account Manager.

# Import Data with Excel {#import-excel}

OMD Go is an online service and therefore requires strong import/export capabilities. When starting with a new configuration, uploads with Excel files are very common and useful since it is easier to gather data in a spreadsheet up-front and upload that data rather than entering the data manually through the web interface.

<a href="assets/sample.xls" target="_sample">This Sample Excel document</a> will help you to collect the information. The document contains several worksheets. In a first step, you may only want to fill the `Resource` and the `Task` worksheets. Remove all irrelevant worksheets and columns before uploading. Once the document is finalized, upload the document by opening the configuration and selecting the `Planning > Data Up-/Download > Upload Data` menu option.

# XML Upload

For a fully integrated production environment, you may want to automate data uploads, for example, to inform Optimize My Day about a new task created by the ERP that needs to be scheduled. In those cases, we use [XML](http://en.wikipedia.org/wiki/Xml) documents for data exchange, a flexible and easy way of interchanging data over the internet. Continue reading <a href="../integration/uploads/index.html">XML Uploads</a> for more details.

## Upload Errors

When posting data to Optimize My Day through the Upload Service, information about errors during the upload will be returned by the Upload Service itself. The OMD Client can process the result by parsing the returned XML and take appropriate action. For administrators, it can be useful to monitor these errors for all clients, using the Upload Errors Forward Service.

By specifying an e-mail or a comma-separated list of e-mails in the `forwardEmailUploadErrors` preference, all upload errors are sent to the recepients specified in the preference. They will receive an e-mail with the resulting XML attached to it. The body of the e-mail contains a human-readable report about all data that caused errors. A common error is, for example, an invalid reference to a non-existing resource or status code.

### Setup

In the parameter `forwardEmailUploadErrors`, specify the e-mail address or a comma-separated list of e-mails to OMD should forward an Upload Error Report to.

### Usage

If not specified, the Upload Error Report will be forwarded to the owner of the configuration.
