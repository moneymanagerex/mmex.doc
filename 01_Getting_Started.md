Chapter 1: Getting Started

# What is Money Manager Ex?

Money Manager Ex (hereinafter referred to as _MMEX_) is a free and open source software

designed for language learning. It serves as a simple and user-friendly tool for you to control and monitor your personal finances. It was developed to address your need for a tool to maintain good financial records and make informed decisions.

MMEX allows you to track activities in multiple accounts and different currencies at the same time. Its purpose is to help you build better personal financial habits. It was created with the vision that you would use the software everyday to keep comprehensive records of your income, expenses, assets, and make informed decisions on investments and budget accordingly.

MMEX allows you to easily import and export data from any CSV and QIF formats. With its unique built-in report generator, you can quickly and easily create comprehensive charts, graphs, and reports. You can also schedule transactions and set reminders for recurring bills and paychecks. With everything stored in a Non-Proprietary SQLite Database with AES Encryption, you can be reassured that your financial information is safe and secure with MMEX.

With a diverse and global team, we have contributors providing user support from all around the world. As of December 2020, we have international language support available in 24 languages.

# The Home Interface

The Home Interface shows you your list of accounts and a brief overview of your financial activities. This interface is blank by default when you first create a database. You can view and access your financial information here after adding new accounts and information on financial activities like transactions.

The MMEX interface has the following components:

- The _Navigation panel_ on the left shows a hierarchical structure of all the interfaces and related sections, such as accounts, assets, and recurring transactions. See navigation panel for more.
- The _Top Menu bar_ contains various menu items for easy shortcut actions in the software. See Top menu bar for more.
- The _Workspace_ area displays information about the section you are working with. For example, your cash account and related transactions.

## The Navigation panel

_The Navigation panel displays all the interfaces as a hierarchical tree structure. You can navigate to different interfaces from here._

\&lt;table\&gt;

## The Top Menu bar

_The Top Menu bar contains various menu items for easy shortcut actions in the software._

| item | Icon  | Function  |
|---|---|---|
| New Database | ![img](https://openclipart.org/image/32px/svg_to_png/25697/Architetto----Database.png) | Create a new database |
| Open Database | ![img](https://openclipart.org/image/32px/svg_to_png/32215/document-open.png) | Open an existing database |
| New Account | ![img](https://openclipart.org/image/32px/svg_to_png/27766/ronoaldo-New-Document.png) | Create a new acount |
| Account List | ![img](https://openclipart.org/image/24px/svg_to_png/30805/go-home.png) | Return to the Home interface and show the account list |
| Show Organize Categories Dialog | ![img](https://openclipart.org/image/32px/svg_to_png/20404/richardtallent-Blue-Tag.png) | Display Organize Categories Dialog |
| Show Organize Payees Categories Dialog | ![img](https://openclipart.org/image/32px/svg_to_png/119149/man-chris-kempson-01.png) | Display Organize Payees Categories Dialog |
| Show Organize Currency Dialog | ![img](https://openclipart.org/image/32px/svg_to_png/172798/dollar.png) | Display the Organize Currency Dialog |
| Transaction Report Filter |  | Filter transactions for review |
| General Report Manager |  | Display the General Report Manager Dialog |
| Options Dialog | ![img](https://openclipart.org/image/32px/svg_to_png/22436/nicubunu-Tools.png) | Display the Options dialog |
| New Transaction |  | Create a new transaction |
| Register/View Release Notifications | ![img](https://openclipart.org/image/32px/svg_to_png/212153/rodentia-icons_accessories-news-reader.png) | Display release notificaitons in a brower |
| Download Currency and Stock Rates |  | Download currency and stock rates from your defined sotck quote web page |
| Toggle Fullscreen |  | Toggle fullscreen |
| Print current view  | ![img](https://openclipart.org/image/32px/svg_to_png/32227/document-print.png)   | Print the current workspace view  |
| Show about dialog  | ![img](https://openclipart.org/image/32px/svg_to_png/168141/star2.png) |  Display the About dialog |
|  Show the Help Page |   | Display the Money Mager Ex User Manual  |

# Settings and Preferences

The overall look-and-feel of the application can be configured and may not appear as

seen in this documentation depending on your setup, but general functionality remains

the same. Use the Options dialog (Tools \&gt; Options) to change settings. These are the available setting categories:

- General: This category contains configuration options for display heading, base currency, date format, financial year, and transaction sound and dates.
- View Options: This category contains configuration options for display like icon size, visible accounts, and HTML scale factor.
- Attachments: This category contains configuration options for attachments. This category is only applicable for Windows users.
- Network: This category contains configuration options for the MMEX WebApp.
- Others : This category contains configuration options for the stock quote web page, New Transaction Dialog settings, database backup, and CSV settings.

![](RackMultipart20201122-4-170d848_html_d7d96b5ac06910ee.png)

\&lt;h2\&gt;each category\&lt;/h2\&gt;

\&lt;table\&gt;

\&lt;h2\&gt;each category\&lt;/h2\&gt;

\&lt;table\&gt;

\&lt;h2\&gt;each category\&lt;/h2\&gt;

\&lt;table\&gt;

\&lt;h2\&gt;each category\&lt;/h2\&gt;

\&lt;table\&gt;

\&lt;h2\&gt;each category\&lt;/h2\&gt;

\&lt;table\&gt;

## Configuring the settings

_Refer to tables 1-3, 1-4, 1-5, 1-6 and 1-7 for the properties you can configure for MMEX._

To configure the settings

1. Select a category you wish to configure.
2. Select a property you wish to configure.
3. Configure the setting as required.
4. Select **Apply** to apply changes to the category and continue configuring the settings.

Or

Select **Ok** to apply changes and close the Options dialog.

# About database

This section helps you manage your MMEX database. Your MMEX is empty by default when

you first install the software, and you are prompted to create a new database when you initially launch it. To start using MMEX, you can create a new database. You can maintain multiple MMEX databases on the same computer at the same time. You can select where on your machine you want to store the databases.

## Creating a new database

_You can create a new database to start using MMEX._

To create a new database

1. Select **New Database** from the Top Menu bar.
2. Navigate to a desired location on your computer.
3. Enter a file name and select **Save.**

# About accounts

This section helps you manage your MMEX accounts. You can create multiple accounts and with different currencies within a single database. Your database is empty by default when you initially create it. To start managing your personal finance, you can create a new account.

## Account Types

There are eight types of accounts you can create in MMEX, and the Add Account Wizard makes it easier to do so. These are the types of accounts MMEX supports:

- Cash
- Checking
- Credit card
- Loan
- Term
- Investment
- Asset
- Shares

## Creating a new account

You can create a new account with the Add Account Wizard.

To create a new account

1. Select **New Account** from the Top Menu bar.

The Add Account Wizard displays.

1. Read the texts and select **Next**.
2. From the drop-down menu, select the type of account you wish to create and select **Next**.
3. Enter a name for the account and select **Finish**.

The Edit Account dialog displays.

1. Configure the settings as required.
2. Select **OK** to create the account.
