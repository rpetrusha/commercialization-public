---
author: joshbax-msft
title: iSCSI HBA RedirectionTest (LOGO)
description: iSCSI HBA RedirectionTest (LOGO)
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 954c2cf1-ac23-49e7-a630-bc6ca14bbf7c
---

# iSCSI HBA RedirectionTest (LOGO)


This test verifies that a host-bus adapter (HBA) properly handles the target device's capability to redirect the connection to a different IP address or port.

## Test details


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Associated requirements</strong></p></td>
<td><p>Device.Storage.Controller.Iscsi.Interface</p>
<p>[See the device hardware requirements.](http://go.microsoft.com/fwlink/p/?linkid=254483)</p></td>
</tr>
<tr class="even">
<td><p><strong>Platforms</strong></p></td>
<td><p>Windows 7 (x64) Windows 7 (x86) Windows 8 (x64) Windows 8 (x86) Windows Server 2012 (x64) Windows Server 2008 R2 (x64) Windows Server 2008 x64 Windows Server 2008 x86Windows 8.1 x64Windows 8.1 x86Windows Server 2012 R2</p></td>
</tr>
<tr class="odd">
<td><p><strong>Expected run time</strong></p></td>
<td><p>~5 minutes</p></td>
</tr>
<tr class="even">
<td><p><strong>Categories</strong></p></td>
<td><p>Certification Functional</p></td>
</tr>
<tr class="odd">
<td><p><strong>Type</strong></p></td>
<td><p>Manual</p></td>
</tr>
</tbody>
</table>

 

## Running the test


Before you run the test, complete the test setup as described in the test requirements: [iSCSI HBA Testing Prerequisites](iscsi-hba-testing-prerequisites.md).

If this is the first time you are running an iSCSI HBA test, iSCSI Target test, or MPIO test over iSCSI bus type on the HCK client, or if there is no iscsihctconfig.ini under \[HCK Path\]\\JobsWorkingDir\\ on the HCK client, you will receive a pop-up dialog box to input iSCSI configuration information and/or HBA information. For more information about this dialog box, see “Running the test” in [iSCSI HBA Boot Test (LOGO)](iscsi-hba-boot-test--logo-ca7ad4d0-6950-4e2d-bdfe-b80c7873ba90.md).

## Troubleshooting


For troubleshooting information, see [Troubleshooting Device.Storage Testing](troubleshooting-devicestorage-testing.md).

In addition:

1.  Look at the job results log file for test failures.

2.  Enter the required data in the configuration dialog box that appears when this job is scheduled. For more information, go to [iSCSI HBA Boot Test (LOGO)](iscsi-hba-boot-test--logo-ca7ad4d0-6950-4e2d-bdfe-b80c7873ba90.md).

This test always return Pass or Fail. To review test details, review the test log from the Windows HCK Manager.

## More information


This test implements a simple iSCSI target. The test performs a logon to this target by using the HBA under test. The target, when it receives the first logon packet, will redirect the HBA to connect to the target by using a different location.

The test has three different variations that use different redirection mechanisms:

1.  Redirection to a new IP address

2.  Redirection to a new IP address and new port

3.  Redirection to the same IP address with a new port

To run this test:

1.  Run the test as a DTM job.

2.  Fill the required data in the configuration UI that pops up when this job is scheduled.

### Parameters

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LogVerbosity</p></td>
<td><p>The verbosity of logging. There are three levels of output: 0, 1, and 2. 2 is the most verbose.</p>
<p>Default value: 1</p></td>
</tr>
</tbody>
</table>

 

### Command syntax

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Command option</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Iscsi_redirect.exe -hct -v [LogVerbosity]</strong></p></td>
<td><p>Runs the test. The <strong>–v</strong> option controls the verbosity of the logging. There are three levels of output: 0, 1, and 2. 2 is the most verbose.</p>
<p>Default value: 1</p></td>
</tr>
</tbody>
</table>

 

**Note**  
For command-line help for this test binary, type **/h**.

 

### File list

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>File</th>
<th>Location</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Iscsi_redirect.exe</p></td>
<td><p><em>&lt;[testbinroot]&gt;</em>\nttest\driverstest\storage\wdk\iscsi\</p></td>
</tr>
</tbody>
</table>

 

 

 





