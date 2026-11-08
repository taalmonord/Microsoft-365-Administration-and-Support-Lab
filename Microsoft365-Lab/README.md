# Microsoft 365 User Support and Administration Lab

## Status
In progress. Windows 11 client preparation; Microsoft 365 tenant and services not yet configured or verified.

## Evidence log

### 01 Windows 11 network configuration before correction
- Screenshot: screenshots/01-dns-configuration-before-correction.png
- Preferred DNS entered: 192.168.60.10 (intended lab domain controller; not verified by this screenshot).
- Alternate DNS blank.
- Static IPv4 selected with IP address, subnet mask, and gateway blank. This is an incomplete configuration, not successful setup evidence.
- Next action: select Obtain an IP address automatically if using lab DHCP; keep manually specified domain-controller DNS. Validate client IP configuration and domain DNS resolution afterward.
- Retain as troubleshooting evidence; replace with verified final-state evidence for the main project walkthrough.

## Documentation approach
Keep screenshots demonstrating meaningful configuration, test results, and troubleshooting. Routine or redundant screens need not be included in the final walkthrough. Do not treat screenshots of entered settings as proof they were applied or worked.

### 02 Corrected client network configuration
- Screenshot: screenshots/02-client-dhcp-and-domain-dns.png
- Obtain an IP address automatically selected.
- Preferred DNS set to 192.168.60.10; alternate DNS blank.
- Screenshot captures intended settings; it does not show the assigned client IP or DHCP lease.

### 03 Domain DNS lookup validation
- Screenshot: screenshots/03-domain-dns-resolution.png
- Command: nslookup corp.adtraining.com
- Responding DNS server: DC01.corp.adtraining.com, 192.168.60.10.
- Result: corp.adtraining.com resolves to 192.168.60.10.
- Establishes a successful lookup through DC01; does not by itself establish domain membership, AD SRV discovery, or Microsoft 365 connectivity.
- Next milestone: join the Windows 11 client to corp.adtraining.com and verify domain-user sign-in.

### 04 Domain join configured; restart pending
- Screenshot: screenshots/04-domain-join-restart-pending.png
- System Properties shows computer Windows-11.corp.adtraining.com and domain corp.adtraining.com.
- Windows explicitly indicates changes take effect after restart.
- Next action: restart client, then verify domain membership and domain-user sign-in. No successful domain-user sign-in established yet.

### 05 Microsoft 365 Business Premium trial signup completed
- Screenshot: screenshots/05-business-premium-trial-created.png
- Confirmation shows completed signup and NorthNAtlantic.onmicrosoft.com tenant sign-in domain.
- Page states paid subscription begins after trial unless canceled by December 6, 2026.
- Recurring billing disabled status NOT established. Next: open admin center, Billing > Your products, select trial and turn off recurring billing; verify expiry rather than renewal.
- Original screenshot includes personal account and order details; retain locally and redact before any public portfolio publication.

### 06-07 Cloud test users and standard roles
- Screenshots: screenshots/06-carl-blark-standard-user.png and screenshots/07-tiffany-marks-standard-user.png.
- Accounts visible: Carl Blark and Tiffany Marks, using NorthNAtlantic.onmicrosoft.com usernames.
- Both account panes explicitly show Roles: No administrator access.
- Both display group membership named NorthNAtlantic; site access has not been tested. Check inherited/group access when designing the private SharePoint denied-access exercise.
- These screenshots do not show assigned licenses or successful user sign-in.
- Next evidence requested: Active users list with both users and Licenses column visible, then successful user sign-in.

### 08 Active users and license assignments
- Screenshot: screenshots/08-active-users-licenses.png.
- Active users list shows Carl Blark, Tiffany Marks, and the lab administrator.
- All three rows show Microsoft 365 Business Premium assigned.
- Combined with screenshots 06-07, confirms both test accounts exist, have licenses assigned, and have no administrator access.
- Does not establish successful sign-in, mailbox availability, or service testing.
- Next milestone: test-user sign-in in a separate browser session, followed by Outlook mail flow testing.

### 09 Carl test-user sign-in and mailbox access
- Screenshot: screenshots/09-carl-outlook-sign-in.png.
- Outlook inbox loads with account menu identifying Carl Blark.
- Confirms Carl can sign in and open his mailbox. Does not establish mail sending or receiving, Tiffany sign-in, or use of InPrivate (browser frame not shown).
- Next test: send a clearly labeled lab email from Carl to Tiffany, verify receipt as Tiffany, reply, and verify receipt as Carl.

### 10-12 Outlook mailbox and internal mail-flow validation
- Screenshot 10: Tiffany Marks account menu and loaded Outlook inbox confirm mailbox access.
- Screenshot 11: Tiffany inbox displays a received message from Carl; reply is still a draft in this image.
- Screenshot 12: Carl inbox displays Tiffany reply and the original message, establishing successful internal delivery in both directions.
- Compose-only screenshot omitted as redundant; composition alone does not establish delivery.
- Message content uses a patient-appointment scenario. Whether all details are fictional has not been explicitly confirmed; do not publish these screenshots until confirmed synthetic, or replace with explicitly labeled fictional lab messages.
- Scope: Outlook on the web and internal tenant mail flow only. Desktop Outlook and external delivery not tested.
- Next planned milestone: Teams membership and test conversation, followed by private SharePoint access tests and OneDrive sync.

### 13-14 Teams setup and membership notification
- Screenshot 13 shows Teams web with IT Support Lab present and Tiffany Marks selected as Member in the add-members dialog. Add is still visible; this image alone does not prove completed addition.
- Screenshot 14 shows an email addressed to Tiffany reporting Carl added her to IT Support Lab, corroborating completed addition.
- Team privacy and final owner/member list not shown; no channel-message exchange verified yet.
- Next evidence: Manage team membership list, privacy setting, and a post/reply exchange between test users.

### 15-16 Teams membership and channel collaboration verified
- Screenshot 15 shows IT Support Lab with Carl Blark as Owner and Tiffany Marks as Member.
- Screenshot 16 shows Carl channel post and Tiffany reply confirming channel access.
- Intermediate post-only screenshot omitted as redundant.
- Establishes team-level roles and successful channel participation. Team ownership is distinct from tenant administrator roles.
- Private team setting not yet shown. Next requested evidence: team privacy configuration.
- Future SharePoint denied-access test must use a separate private site excluding Tiffany; the team-connected site may grant her access through this team membership.

### 17 Teams privacy verified
- Screenshot: screenshots/17-teams-private-setting.png.
- Edit team details displays IT Support Lab privacy as Private - Only team owners can add members.
- Combined evidence: private team configuration, Carl Owner, Tiffany Member, and successful channel post/reply.
- Teams milestone complete for the planned basic membership and collaboration test. No calls, meetings, desktop client, or troubleshooting incident tested.
- Next milestone: separate private SharePoint site for a controlled access-denied and approved-access exercise; exclude Tiffany initially, including any groups granting access.

### 18 SharePoint successful-access baseline
- Screenshot: screenshots/18-sharepoint-carl-access-baseline.png.
- Site title: (Lab Test) HealthConceptsLtd. Site header shows Private group.
- Account menu identifies Carl Blark; site home loads successfully.
- Confirms Carl site access, not document editing or OneDrive sync.
- Next controlled test: open the same site as Tiffany in an isolated browser session; capture actual access result before changing membership.

### 19 Controlled SharePoint denied-access test
- Screenshot: screenshots/19-sharepoint-tiffany-access-denied.png.
- Account menu identifies Tiffany Marks; page explicitly states You need access / You do not have access to this item.
- Captured after user opened the instructed lab-site URL; browser address bar not visible in evidence.
- Combined with licensed-user evidence and Carl successful site access, supports a deliberately simulated site-authorization issue rather than treating the license as the access grant.
- This restriction is expected by design, not a confirmed platform malfunction. Next: inspect site membership as owner, grant Tiffany approved Member access for the lab, capture membership, then verify site access as Tiffany.

### 20-21 SharePoint membership correction and successful retest
- Screenshot 20 shows group membership: Talamas Almonord Owner, Carl Blark Member, Tiffany Marks Member.
- Screenshot 21 shows the private (Lab Test) HealthConceptsLtd site loaded with account menu identifying Tiffany Marks.
- Together with screenshot 19, establishes controlled before/after test: Tiffany initially denied, membership granted, then site access successful.
- Lab scenario: an intentionally excluded licensed user requires approved site membership. This is a simulated authorization support case, not a product defect or a real employer incident.
- Scope: site home access verified. Document editing, sync, and OneDrive client setup remain untested.
- Next milestone: create a fictional test document in the site Documents library, verify editing, then configure and validate library sync using OneDrive on the Windows 11 client.

### 22 SharePoint document saved
- Screenshot: screenshots/22-sharepoint-test-document.png.
- Documents library contains Lab Support Test.docx, modified by Tiffany Marks.
- Supports saved document creation/modification under Tiffany identity. Contents and exact text not visible; no desktop sync established.
- Next: deselect the file and locate library Sync action (may be in toolbar overflow) to configure OneDrive client sync on Windows 11.

### 23 OneDrive setup PC-folder backup error
- Screenshot: screenshots/23-onedrive-folder-backup-error.png.
- OneDrive Back up folders on this PC shows Documents, Pictures, Desktop unable to sync, all toggles off.
- Unknown error code 0x8004016c shown. Root cause not established.
- This concerns PC known-folder backup; it does not establish failure of SharePoint document-library sync.
- PC-folder backup is outside the planned library-sync test. Leave toggles off and attempt Next if available; inspect subsequent setup and sync status before claiming success.

### 24 SharePoint library visible in Windows File Explorer
- Screenshot: screenshots/24-sharepoint-library-file-explorer.png.
- NorthNAtlantic organization node contains a folder labeled (Lab Test) HealthConceptsLtd - Docume... with a blue cloud status icon.
- Establishes library integration visible in Explorer; exact folder name truncated. File contents, sync health, client account identity, and bidirectional synchronization not yet verified.
- Blue cloud indicates online-only availability, not by itself an error.
- Next: open library folder, verify Lab Support Test.docx appears, then perform controlled local-to-cloud file test.

### 25 SharePoint document visible locally
- Screenshot: screenshots/25-sharepoint-document-local-availability.png.
- Explorer path shows NorthNAtlantic > (Lab Test) HealthConceptsLtd - Documents.
- Lab Support Test.docx appears, 22 KB, with outlined green check status (locally available).
- Corroborates cloud-created document appearing in synced Windows library. Does not prove local-to-cloud upload or document contents.
- Next: create Sync-Test.txt in this library locally using Notepad, then verify it and its contents in SharePoint web.

### 26 Local upload test saved outside library
- Screenshot: screenshots/26-sync-test-wrong-folder.png.
- Sync-test text document sits in NorthNAtlantic parent folder alongside the actual (Lab Test) HealthConceptsLtd - Documents library folder.
- This location does not establish library sync or upload. Correct destination is inside the Documents library folder containing Lab Support Test.docx.
- Next: move only Sync-test.txt into the library folder, then verify file and contents through SharePoint web. No upload success claimed yet.

### 27 Local sync test moved into correct library folder
- Screenshot: screenshots/27-sync-test-correct-library-folder.png.
- Explorer breadcrumb shows NorthNAtlantic > (Lab Test) HealthConceptsLtd - Documents.
- Lab Support Test.docx and Sync-test text document are both present with green check status.
- Confirms corrected local destination and client-reported file status. SharePoint browser receipt/content verification still pending.
- Next: refresh SharePoint Documents in browser, open Sync-test.txt, and compare its contents with the local test text.

### 28 Local test file received in SharePoint web
- Screenshot: screenshots/28-sync-test-visible-sharepoint-web.png.
- SharePoint Documents library shows Sync-test.txt and Lab Support Test.docx, both modified by Tiffany Marks.
- With local-file screenshots and the documented move into the synced folder, verifies local-to-cloud file appearance.
- Cloud-created Word document also previously appeared locally: basic transfer demonstrated in both directions using separate files.
- Text contents in cloud have not been inspected. Next final check: open Sync-test.txt in web and confirm exact expected sentence.

### 29 Cloud content verified; basic sync milestone complete
- Screenshot: screenshots/29-sync-test-cloud-content-verified.png.
- SharePoint preview of Sync-test.txt contains: Created locally to test SharePoint upload through OneDrive
- Matches local Notepad content previously supplied. Local-to-cloud file/content validation complete.
- Basic cloud-to-client file availability was established for Lab Support Test.docx; no offline-edit conflict or continuous bidirectional editing test claimed.

## Verified milestone summary
- Two licensed standard cloud users, Carl Blark and Tiffany Marks.
- Both Outlook web mailboxes accessed; internal message and reply delivery verified.
- Private Teams team, owner/member roles, and channel conversation verified.
- Private SharePoint site: Carl baseline access, Tiffany denied, Tiffany membership granted, Tiffany access retested successfully.
- SharePoint Word document saved by Tiffany and available locally through OneDrive library sync.
- Locally created text file transferred through synced library and contents verified in SharePoint web.
- Known-folder backup error 0x8004016c retained as a separate unresolved setup issue; successful document-library test does not establish that error was repaired.
- Domain-join restart and domain-user sign-in not evidenced beyond pending-restart screenshot.
- Recurring billing reported off by user; no confirmation screenshot retained.
- Before public publication, confirm appointment-email content is entirely fictional or replace those images; review screenshots for personal account and order details.
