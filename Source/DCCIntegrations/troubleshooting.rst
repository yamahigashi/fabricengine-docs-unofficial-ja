.. _troubleshooting:

Fabric Engine |FABRIC_VERSION| Trouble Shooting
==========================================================

.. image:: /images/FE_logo_345_60.*
   :width: 345px
   :height: 60px

| Fabric Engine version |FABRIC_VERSION|
| |FABRIC_COPYRIGHT|

If Fabric Engine |FABRIC_VERSION| doesn't run for you, or your are hitting any problem when running it, please review the hints below first. If this document doesn't resolve your issue, please refer to the feedback section at the end of this document.

1.Compatible Operating Systems
------------------------------

Fabric Engine |FABRIC_VERSION| currently supports the following operating systems (only). Windows 7 prior to SP1 is not supported. 32 bit operating system versions are currently not supported.

	- Windows 7 64-bit SP1
	- Windows 8 64-bit (or higher)
	- Ubuntu 12.04 64-bit
	- CentOS 6.3 64-bit
	- OSX

2.Compatible DCC Software
------------------------------

Fabric Engine |FABRIC_VERSION| is distributed for a specific list of DCCs, and specific versions of each one. Other versions are not supported. Each DCC integration is delivered as source code however, and can be build from source for other versions if required. Please refer to :ref:`DCCINTEGRATIONS` for more information.

  - Maya 2012 on Windows
	- Maya 2013 SP1 on Windows
	- Maya 2014 SP1 on Windows
  - Maya 2014 SP2 on Windows
	- Maya 2015 SP2 on Windows
  - Maya 2012 on Linux
	- Maya 2013 SP1 on Linux
	- Maya 2014 SP1 on Linux
  - Maya 2014 SP2 on Linux
	- Maya 2015 SP2 on Linux
	- Maya 2014 SP1 on OSX
  - Maya 2014 SP2 on OSX
	- Maya 2015 SP2 on OSX
	- Softimage 2013 SP1 on Windows
	- Softimage 2014 SP1 on Windows
  - Softimage 2014 SP2 on Windows
	- Softimage 2015 SP2 on Windows
	- Softimage 2014 SP1 on Linux
  - Softimage 2014 SP2 on Linux
	- Softimage 2015 SP2 on Linux
	- Nuke 7.0v8 on Windows
	- Nuke 7.0v8 on Linux
	- Nuke 7.0v8 on OSX
	- Arnold 4.0.15.1 on Windows
	- Arnold 4.0.15.1 on Linux
	- Arnold 4.0.15.1 on OSX
	- Any OpenFX host on Windows (Sony Vegas, Toxic, Nuke, Fusion)
	- Any OpenFX host on Linux (Sony Vegas, Toxic, Nuke, Fusion)
	- Any OpenFX host on OSX (Sony Vegas, Toxic, Nuke, Fusion)

3. Environment variables
------------------------

Fabric Engine |FABRIC_VERSION| relies on several environment variables to be set. These can be used to extend the functionality, but need to be set initially to run Fabric Engine. Most integrations automate this process, however you might have to set them manually to be able to run Fabric Engine. Note that other |FABRIC_COMPANY_NAME| products might be using the same environment variables, so it's recommended to use dedicated launcher scripts for each application. Using another product's environment variables might cause incompatibility issues between Core library versions, for example. A typical issue created by the :envvar:`PATH` variable not being set correctly is a :dfn:`Procedure not found` error. The required environment variables are:

	- :envvar:`FABRIC_EXTS_PATH`
	  
	  Usually set to the Exts folder coming with each Fabric Engine integration. This variable is used to locate KL extensions, such as the Alembic extension, for example. Can contain a list of folders.
	- :envvar:`PATH` (Windows) / :envvar:`LD_LIBRARY_PATH` (Linux, OSX)
	  
	  Since Fabric Engine is linked dynamically against |FABRIC_COMPANY_NAME| Core library, the library will need to be on the :envvar:`PATH` / :envvar:`LD_LIBRARY_PATH`. For most integrations the folder to add to the :envvar:`PATH` / :envvar:`LD_LIBRARY_PATH` is the same folder that holds the actual plugin / dll / .so.

4. Licensing
------------

If you are experiencing slowdowns when running Fabric Engine (pause of 15 seconds) or Fabric Engine isn't running for you at all, this might be related to licensing. Make sure to inspect any script log or standard out feedback for licensing messages. To resolve licensing issues, please check the :ref:`LG`

5. Maya User Preferences
-----------------------------

Since Maya stores hotkey and runtime command information in its user preferences files, it's possible that you might experience issues related to menu entries or custom contexts (interactive tools) within Maya. Fabric Engine sets up missing hotkeys or runtime commands automatically, so it is best to remove previous runtime commands and hotkeys. To do that, find you maya user preferences folder, find the :dfn:`userHotKeys.mel` and :dfn:`userRuntimeCommands.mel` files, edit them and remove any Fabric Engine related lines.

6. Maya PySide related issues
------------------------------
Maya comes with its own version of PySide (or PySide2 starting in Maya 2017). When launching maya from the console after source the fabric environment this might cause issues. If you experience any hick-ups concerning PySide inside of Maya when launching maya from the console please make sure that the Fabric folders are listed ``after`` the Maya related python folders in the :envvar:`PYTHONPATH`.

7. Provide Feedback
----------------------

If this document didn't resolve your issue, please contact the general Fabric Engine email list (or your dedicated support email list). Please create an issue on the `Fabric Engine Issue Tracking <mailto://bugs@fabricengine.com>`_.. 
