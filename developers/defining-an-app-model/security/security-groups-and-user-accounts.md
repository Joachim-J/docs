# Security groups and user accounts

Genus Apps uses a **user or computer account** to authenticate the identity of the user or computer, and to authorize or deny access to application resources (data and functions). The account establishes an identity for the user. The identity is then used to authenticate the user and to grant the user authorization to access specific application resources.

You collect users, computers and other groups into a **security group**_,_ and then assign appropriate privileges and permissions to the security group. This simplifies administration by letting you assign privileges and permissions once to the group instead of multiple times to each individual user. When you add a user to an existing group, the user automatically gains the privileges and permissions already assigned to that group. Another feature that makes it easier to manage users is that you can nest groups, that is, you can add a group as a member of another group. This is referred to as the [effective memberships](effective-memberships-and-permissions.md "Effective Memberships and Permissions") for a group or user account.

The following built-in users and groups are available:

<table style="WIDTH: 100%">

<tbody>

<tr>

<th>Name</th>

<th>Type</th>

<th>Description</th>

</tr>

<tr>

<td>Guest</td>

<td>User</td>

<td>Anonymous [Web Services](../services/web-services/index.md) run as this user. Permissions and memberships must be granted as necessary.</td>

</tr>

<tr>

<td>Service</td>

<td>User</td>

<td>[Logical Services](../../installation-and-configuration/configure-and-maintain-genus-server/genus-server--logical-services.md) run as this user. Permissions and memberships must be granted as necessary.</td>

</tr>

<tr>

<td>Everyone</td>

<td>Group</td>

<td>All users are automatically members of this group. Users and groups cannot be added as members explicitly. Memberships to other groups cannot be added.</td>

</tr>

<tr>

<td>App Administrators</td>

<td>Group</td>

<td>Members of this group have the option to run the application with highest privileges. User members can be added, but only from within the group itself. Other groups cannot be added as members. Memberships to other groups cannot be added.</td>

</tr>

</tbody>

</table>

## Add a security group

Required [security privilege](security-privileges.md): **Administer Security Groups**.

1.  [Open Genus Studio](../getting-started/how-to-open-genus-studio.md).
2.  In the **Directory** tree, expand the **Security** folder, and then click the **Groups** folder.
3.  On the toolbar, click **New**![ID72DD9A50754F4903.IDB8369AB86B864B52.jpg](media/ID72DD9A50754F4903.IDB8369AB86B864B52.jpg).
4.  In the **Name** box, type a name for the Security Group.
5.  Optionally type an identifier in the **Identifier** box. The identifier has to be unique. If users are imported from another system, you can use the identifier to assign group memberships to users.
6.  Optionally type a description in the **Description** box.
7.  To add existing groups or users as member of the group, click the **Members** tab.
8.  To add one or more users as members of the group, click **Add Users**. To add one or more groups as members of the group, click **Add Groups**. Type the name of the group or user you want to add, and then click **OK**.
9.  To include the group as a member of another group, click the **Member Of** tab, and then click **Add**. Type the name of the group, and then click **OK**.
10.  To view the [effective memberships](effective-memberships-and-permissions.md "Effective Memberships and Permissions") for the group, click **Memberships**.
11.  To grant permissions to the group, click the **Security** tab. Follow the [step-by-step procedure](security-permissions.md) on how to grant permissions to an object.

## Add a user- or computer account

Required [security privilege](security-privileges.md): **Administer users**.

Computer accounts can only be added if users are authenticated by MicrosoftB. Active Directory. Genus Apps provides two mechanisms for user authentication: [Custom authentication and Active Directory authentication](../logic/action-orchestration/actions/effects/genus-app-services-user-authentication.md "Genus Services User Authentication"). How users are authenticated is defined in [Genus Configuration](../../installation-and-configuration/configure-and-maintain-genus-server.md).

When you add a user account, you have to select an [account profile](account-profiles.md) for the user. The profile describes the password- and lockout policy for a user, and optionally a description on how to associate a user account with a business object. For example, a user account can be associated with an employee. If users are authenticated by MicrosoftB. Active Directory, the password- and lockout policy is determined by Active Directory.

If your application uses **custom authentication**, follow these steps:

1.  [Open Genus Studio](../getting-started/how-to-open-genus-studio.md).
2.  In the **Directory** tree, expand the **Security** folder, and then click the **Users** folder.
3.  On the toolbar, click **New**![ID398340EF4A3244CA.ID28F0DE726047425A.jpg](media/ID398340EF4A3244CA.ID28F0DE726047425A.jpg).
4.  In the **User Account Wizard**, select an account profile for the user. This page is only displayed if more than one account profile is available.
5.  Click **Next**.
6.  If the selected account profile is associated with an Object Class, select which data set to search and type a name for the object you want to associate with the user account. Click **Next**. If the account profile not is associated with an Object Class, continue to step 10\.
7.  In the **Search Result** list, select which object to associate with the user account.
8.  Click **Next**.
9.  Type a sign in name, a name and a mail address for the user. If the account profile is associated with an Object Class, this information is filled in based on the object selected above.
10. Select the **App Model Admin** check box if you want to grant app model admin rights to the user. This option is not available if you do not have app model admin rights.
11.  Type a password in the **Password** box.
12.  To force the user to change password at next sign in, click **Account must change password at next sign in**.
13.  Click **Next**.
14.  To include the user as a member of one or more groups, click **Add**. In the **Select Groups** dialog box, type the name of the group, and then click **Check Names**. Click **OK**.
15.  Click **Next**.
16.  In the **Language** box, select the default language for the user. In the **Display Format Web** box, select the formatting culture for the user on web browser clients. In the **Start Page** box, select the page which is initially displayed when the user starts the Genus desktop client. The settings can be modfied by the user in [the personal setup for individual user accounts](../../../users/navigate-view-modify-and-control/personalize-your-genus-desktop.md).
17.  Click **Finish**.

If your application uses **Active Directory authentication**, follow these steps:

**Add a user account**

1.  [Open Genus Studio](../getting-started/how-to-open-genus-studio.md).
2.  In the **Directory** tree, expand the **Security** folder, and then click the **Users** folder.
3.  On the toolbar, click **New**![ID398340EF4A3244CA.IDE15C45886BC34293.jpg](media/ID398340EF4A3244CA.IDE15C45886BC34293.jpg).
4.  In the **User Account Wizard**, select an account profile for the user. This page is only displayed if more than one account profile is available.
5.  Click **Next**.
6.  Type a user name for an Active Directory account.
7.  Click **Next**.
8.  In the **Search Result** list, select which Active Directory account to associate with the user account.
9.  Click **Next**.
10.  The sign in name, name and mail address for the user account is filled in based on the selected Active Directory account.
11. Select the **App Model Admin** check box if you want to grant app model admin rights to the user. This option is not available if you do not have app model admin rights.
12.  Click **Next**.
13.  To include the user as a member of one or more groups, click **Add**. In the **Select Groups** dialog box, type the name of the group, and then click **Check Names**. Click **OK**.
14.  Click **Next**.
15.  In the **Language** box, select the default language for the user. In the **Display Format Web** box, select the formatting culture for the user on web browser clients. In the **Start Page** box, select the page which is initially displayed when the user starts the Genus desktop client. The settings can be modfied by the user in [the personal setup for individual user accounts](../../../users/navigate-view-modify-and-control/personalize-your-genus-desktop.md).
16.  Click **Finish**.

**Add a computer account**

1.  [Open Genus Studio](../getting-started/how-to-open-genus-studio.md).
2.  In the **Directory** tree, expand the **Security** folder, and then click the **Computers** folder.
3.  On the toolbar, click **New**![ID398340EF4A3244CA.ID3B04130E0A194070.jpg](media/ID398340EF4A3244CA.ID3B04130E0A194070.jpg).
4.  In the **Computer Account Wizard**, type a computer name.
5.  Click **Next**.
6.  In the **Search Result** list, select which computer to associate with the computer account.
7.  Click **Next**.
8.  The sign in name and name for the computer account is filled in based on the selected computer.
9.  Click **Next**.
10.  To include the computer account as a member of one or more groups, click **Add**. In the **Select Groups** dialog box, type the name of the group, and then click **Check Names**. Click **OK**.
11.  Click **Finish**.

## View a user account

1.  [Open Genus Studio](../getting-started/how-to-open-genus-studio.md).
2.  In the **Directory** tree, expand the **Security** folder, and then click the **Users** folder.
3.  In the **Search** pane at the top, enter search criteria to find users, and then click **Finish**.
4.  In the table to the right, double click the user, or right-click the user, and then in the shortcut menu, click **Properties**.

User accounts that are locked out are listed in red font color, and user accounts that are disabled are listed in gray font color.

## Change password for a user account

Note that passwords cannot be changed for user accounts authenticated by Microsoft Active Directory.

1.  [Open the user account](security-groups-and-user-accounts.md).
2.  In the **User Account Properties** dialog box, click **Set Password**.
3.  In the **New Password** box, type a password, and then type the password again in the **Confirm New Password** box.
4.  To force the user to change password at next sign in, click **Account must change password at next sign in**.
5.  Click **OK**.

## Disable or enable a user account

1.  [Open the user account](security-groups-and-user-accounts.md).
2.  In the **User Account Properties** dialog box, select the **Account is disabled** check box to disable the user account. To enable the user account, click to clear the **Account is disabled** check box.
3.  Click **OK**.

## Unlock a locked user account

Based on the lockout policy defined in the [account profile setup](account-profiles.md), a user may be locked out after one or more invalid sign in attempts. The account is automatically unlocked after a specified number of minutes. To manually unlock a user, follow these steps:

1.  [Open the user account](security-groups-and-user-accounts.md).
2.  In the **User Acccount Properties** dialog box, clear the **Account is locked out** check box.
3.  Click **OK**.

## Change the default language for a user account

1.  [Open the user account](security-groups-and-user-accounts.md).
2.  In the **Language** box, select the default language for the user. This setting can be modfied by the user in [the personal setup for individual user accounts](../../../users/navigate-view-modify-and-control/personalize-your-genus-desktop.md).

## Change the display format on web browser clients for a user account

Controls the display format of items such as numbers, currency, and dates on web browser clients. If not specified, items are formatted according to the selected language.

1.  [Open the user account](security-groups-and-user-accounts.md).
2.  In the **Display Format Web** box, select the formatting culture for the user. This setting can be modfied by the user in [the personal setup for individual user accounts](../../../users/navigate-view-modify-and-control/personalize-your-genus-desktop.md).

## Change the start page in the navigation pane for a user account

1.  [Open the user account.](security-groups-and-user-accounts.md)
2.  In the **Start Page** box, select the page which is initially displayed when the user starts the Genus desktop application. This setting can be modfied by the user in [the personal setup for individual user accounts](../../../users/navigate-view-modify-and-control/personalize-your-genus-desktop.md).

## Grant app model admin rights to a user account

> [!NOTE]
> App model admin rights replaces the access given to [trusted users](trusted-users.md) in versions prior to 2018.2.

Users with app model admin rights has access to modify the app model in Genus Studio. Only users which have app model admin rights can grant these rights to another user.

1. [Open the user account.](security-groups-and-user-accounts.md)
2. Select the **App Model Admin** check box.

See Also

*   [Security Privileges](security-privileges.md)
*   [Security Permissions](security-permissions.md)
*   [Effective Memberships and Permissions](effective-memberships-and-permissions.md)
*   [Account Profiles](account-profiles.md)
