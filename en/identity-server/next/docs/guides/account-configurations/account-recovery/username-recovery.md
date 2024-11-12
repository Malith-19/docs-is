# Username recovery

Allow users to retrieve their usernames through a self-service process on the login page in {{product_name}}.

## Configuration instructions

To enable username recovery, take the following steps:

1. In the {{product_name}} Console, go to **Login & Registration** > **Account Recovery** > **Username Recovery**.
2. Enable the prefered username channels by selecting the appropriate checkboxes.
    - **Email**: Users can recover their usernames by Email.
    - **SMS**: Users can recover their usernames by SMS.
3. Click **Update** to save the changes.

![Username Recovery Configuration]({{base_path}}/assets/img/guides/account-configurations/username-recovery.png){: width="900" style="display: block; margin: 0;"}

!!! note
    Once users enter their details on the username recovery page, such as their first name, email, or mobile number, if the system can verify a unique user based on the provided information, an email will be sent to their registered email address. If the system is unable to identify a unique user, no recovery information will be sent by default.

    If you want to enable username recovery for non-unique users, you can configure it by adding the following configuration to the `deployment.toml` file located in the `<IS_HOME>/repository/conf` directory.

    ``` toml
    [identity_mgt.username_recovery.non_unique_user]
    enabled = true
    ```

    When this configuration is enabled, the system will send **multiple recovery notifications** with all usernames associated with the identified users.