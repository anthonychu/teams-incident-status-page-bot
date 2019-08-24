# Teams incident status bot

![demo](tailwind-incident-bot.gif)

## Deployment instructions:

- Create the Azure Function app, Storage account, and SignalR Service with this button: [![Deploy to Azure](https://azuredeploy.net/deploybutton.svg)](https://azuredeploy.net/)

- Incident statuses are stored in a table in the Storage account, but there's no way to create this table with ARM. In the Azure portal, open the Storage account and add a table named `statuses`.

- Now navigate to the function app, and open the `teams-webhook` function. Click "Get Function URL" and copy the URL.

    ![Get Function URL](get-func-url.png)

- Finally, open Teams and navigate to the "Apps" page of the team in which you want to create the bot. Click "Create outgoing webhook".

    ![Create outgoing webhook](create-webhook.png)

    Use `StatusPage` as the bot name (this is hardcoded, for now). Paste in the function URL, and enter a description.

    ![Webhook details](webhook-info.png)

    You will be prompted with a secret code for validating webhook calls from Teams. We currently do not use this. Close the dialog box.
