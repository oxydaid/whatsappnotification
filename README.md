# WhatsApp Notification Extension for Paymenter
**Version 1.1.0**

> Automatically send notifications for important transactions and activities directly to your **Admin** and **Customer** WhatsApp numbers. This extension integrates with Paymenter and is optimized for the WhatsApp Gateway service from **wa.oxyda.id**.

## ✨ Key Features
- **Real-time Notifications**: Send instant alerts for every important activity like successful payments, new active services, support tickets, and more.
- **Dynamic Recipient Targeting**: An intelligent system that automatically sends notifications to the Admin, Customer (Buyer), or both, depending on the event type.
- **Detailed & Professional Messages**: Information-rich message templates that include invoice, service, and ticket details, complete with emojis for a more engaging look.
- **Multi-Admin Support**: Send notifications to more than one Admin number simultaneously.
- **Automatic Number Formatting**: Automatically corrects customer phone number formats for indonesian numbers (e.g., from `08...` to `628...`) to ensure reliable delivery.
- **Easy Configuration**: Simple and centralized settings directly within the Paymenter admin panel.

***

## 📋 Prerequisites
Before installing this extension, please ensure you have:
1.  A running installation of **Paymenter**.
2.  A **WhatsApp Gateway** account from **[https://wa.oxyda.id](https://wa.oxyda.id/)**. This extension requires an **API Key** and a **Sender Number (Device)** from that service.

***

## ⚙️ Installation
The installation process is very simple and takes only a few minutes.

1.  **Upload the ZIP file**

    Move the downloaded `WhatsAppNotifications.zip` into your Paymenter `extensions/Others` directory. You can do this with `scp` or `mv` if you downloaded it directly to the server.
    ```bash
    # Example:
    mv WhatsAppNotifications.zip /var/www/paymenter/extensions/Others
    cd /var/www/paymenter/extensions/Others
    ```

2.  **Extract the extension**

    Unzip the archive:
    ```bash
    unzip WhatsAppNotifications.zip
    ```

3.  **Verify the Structure**: Make sure your final file structure is correct, as shown below:
    ```
    /extensions/
    └── 📁 Others/
        └── 📁 WhatsAppNotifications/
            ├── 📄 WhatsAppNotifications.php
            └── 📁 lang/
                ├── 📁 en/
                │   └── 📄 notifications.php
                └── 📁 id/
                    └── 📄 notifications.php
    ```
4.  **Done!** The extension is now ready to be activated and configured from the admin panel.

***

## 🔧 Configuration
After successful installation, activate and configure the extension through the Paymenter admin panel.

1.  Log in to your **Paymenter Admin Panel**.
2.  Navigate to the **Extensions** menu.
3.  Find **WhatsApp Notifications** in the list and click the **Activate** button.
4.  Once activated, go to the **Settings** -> **Extensions** -> **WhatsApp Notifications** menu.
5.  You will see the configuration page. Fill in all the required fields:

    * **API Key**
        * Enter the API Key you obtained from your `wa.oxyda.id` dashboard.
        * > 📝 **Note:** This extension requires a WhatsApp Gateway from https://wa.oxyda.id.

    * **Sender WhatsApp Number (Device)**
        * Enter your device's WhatsApp number registered on `wa.oxyda.id`. For indonesian numbers, use the `62...` format.

    * **Admin WhatsApp Numbers (separate with |)**
        * Enter one or more WhatsApp numbers that will receive notifications as Admin.
        * If there is more than one, separate each number with a vertical bar (`|`).
        * Example: `6281234567890|6289876543210`

    * **Footer Text (Optional)**
        * Text that will be displayed in the footer of each message.

    * **Enable Notifications For Events**
        * Select all the notification types you wish to activate. You can select more than one.

6.  Click **Save** to store your configuration.

***

## 🔔 Notification List
Here is a list of all automated notifications that can be sent by this extension:

| Event | Notification Description | Recipient |
| :--- | :--- | :--- |
| **User Created** | Notifies the admin when a new user registers. | `Admin` |
| **User Updated** | Confirms to the customer & informs the admin that a profile has been changed. | `Admin & Buyer` |
| **Invoice Created** | Sends complete invoice details with total and due date. | `Buyer` |
| **Invoice Paid** | Sends a detailed successful payment confirmation (like a receipt). | `Admin & Buyer` |
| **Invoice Updated** | Sends a notification if an invoice is cancelled or modified by the admin. | `Admin & Buyer` |
| **Service Created** | Confirms that a new service has been created, with its details. | `Admin & Buyer` |
| **Service Updated** | Notifies about a status change on a service (e.g., active, suspended). | `Admin & Buyer` |
| **Ticket Created** | Notifies the admin that a new support ticket has been submitted. | `Admin` |
| **Ticket Replied** | Sends the content of a ticket reply to the admin or customer. | `Admin & Buyer` |
| **Ticket Updated**| Notifies about a status change on a ticket (e.g., open, closed). | `Admin & Buyer` |

***

## 🤔 Troubleshooting / FAQ

* **Notifications are not being sent at all.**
    * Ensure your **API Key** and **Sender Number** are correct.
    * Check the formatting of the **Admin Numbers** (use `|` as a separator).
    * Make sure you have selected the events you want to activate in the **"Enable Notifications For Events"** field.
    * Check the Paymenter log file at `storage/logs/laravel.log` for more detailed error messages.

* **Notifications for Customers (Buyers) are not being sent.**
    * Ensure the customer has a valid phone number in their profile. The extension automatically retrieves the number from the user's profile data.

* **I've changed the code, but there are no changes on the website.**
    * Try running the `php artisan cache:clear` command in your server's terminal to clear the cache.

***

## 📞 Contact & Support
If you encounter any issues or have further questions, please contact us via:

*  **Email**: [info@oxyda.id](mailto:info@oxyda.id)
*  **WhatsApp**: [085258688255](https://wa.me/6285258688255)
*  **Website**: [Oxyda Store](lynk.id/oxyda)
*  **Discord**: [Discord Oxyda](https://discord.gg/bKmj3x6t83)
