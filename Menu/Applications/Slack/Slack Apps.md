Created Slack App

Corp IT
Samba TV

Helpdesk buttons

{
    "text": "Welcome to helpdesk!",
    "attachments": [
        {
            "text": "How can we help you?",
            "fallback": "Open a ticket is unavailable",
            "callback_id": "open_ticket",
            "color": "#6CB3D3",
            "attachment_type": "default",
            "actions": [
                {
                    "name": "ticket",
                    "text": "Open a ticket",
                    "type": "button",
                    "value": "open"
                },
                {
                    "name": "ticket",
                    "text": "Close a ticket",
                    "style": "danger",
                    "type": "button",
                    "value": "close",
                    "confirm": {
                        "title": "Are you sure?",
                        "text": "Confirm.",
                        "ok_text": "Yes",
                        "dismiss_text": "No"
                    }
                }
            ]
        }
    ]
}
