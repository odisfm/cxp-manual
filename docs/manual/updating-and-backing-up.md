---
weight: 5
---

# Updating and Backing up

## Updating ClyphX Pro

The process for updating to a new version of ClyphX Pro is the same as the process for installing ClyphX Pro. All of your settings will remain in place. However, if you have any User Actions that exist within the `user_actions` folder of ClyphX Pro, you will need to back these up before installing the new version of ClyphX Pro. You can use the procedure covered below for backing up.

!!! note "Editor's note"
    See my additions in the [User Actions article](/core-concepts/#user-actions) for details on the new way to deal with user actions and ClyphX upgrades.

## Backing Up Your ClyphX Pro Installation

ClyphX Pro provides a simplified means of backing up your [settings](/core-concepts/#settings-foldersfiles) and any [User Actions](/core-concepts#user-actions) you're using. This is useful when you simply want to back up your installation before updating to a new version of ClyphX Pro or when you need to transfer all of your settings and User Actions to another system.

To create a backup, add an [X-Clip](/core-concepts#x-clips) to the set, name it `[] EXPORT_SETTINGS` and launch it to create a zip file in your [settings folder](/core-concepts/#settings-foldersfiles). The zip file will be named `ClyphX Pro Export x.zip` (where `x` is a timestamp) and will contain two or more folders. Once the backup has been created, install the new version of ClyphX Pro or install ClyphX Pro on the other system and ensure that it's working. You will then restore the backup using the following procedure:

1. Unzip the backup zip file that you created.
2. Delete all of the files in your [settings folder](/core-concepts/#settings-foldersfiles).
3. Copy all of the content within `ClyphX_Pro Settings` and place it in your settings folder.
4. _(Only necessary if you're using User Actions that exist within the user_actions folder of ClyphX Pro)_: Copy all of the content in `ClyphX_Pro User Actions` and place it in the [user_actions](/core-concepts#user-actions) folder.
5. _(Only necessary if you're using User Actions that exist outside of ClyphX Pro)_: Copy all of the content from `External User Actions` and place it in your [_user_actions ](/core-concepts#user-actions) folder.
