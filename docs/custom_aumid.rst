Custom AUMIDs
=====================

How to use
----------

When initialising :class:`~windows_toasts.toasters.InteractableWindowsToaster`, pass the custom AUMID as notifierAUMID

Using an installed AUMID
------------------------
Microsoft.com has a page on `finding the Application User Model ID of an installed app <https://learn.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app>`_.
Below are the ways I recommend

Using Powershell
~~~~~~~~~~~~~~~~
You can use Powershell to view existing AUMIDs.

.. code-block:: powershell

    Get-StartApps

Will return a table of all applications installed for the current user, with the right row containing AUMIDs for each corresponding name.

Using the registry
~~~~~~~~~~~~~~~~~~

#. Open registry editor
#. In the top address bar, paste :code:`HKEY_CURRENT_USER\\Software\\Classes\\ActivatableClasses\\Package`
#. Many Microsoft product AUMIDs should be listed, among other third-party programs


Installing a custom AUMID
-------------------------
Custom AUMIDs can display user-defined titles and icons. The library comes with a script to implement it, :code:`register_hkey_aumid`, registers a AUMID in the registry.
The arguments can be understood using the --help argument. If you have the Python Scripts directory in your path, you should be able to execute them by opening the command console and entering the name of the script.