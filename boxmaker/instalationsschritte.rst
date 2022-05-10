.. _boxmaker-installationsachritte:

Installationsschritte bei erstem einrichten
===========================================

.. tip::
	Alle unten genannten Schritte führt das skript autosetup.bat automatisch aus. Einfach vom Setup-USB-Stick aus starten. Lediglich die UPS Einstellungen müssen noch manuell erledigt werden.

.. warning::
	Warnung
	
.. note::
	Bemerkung
	
.. danger::
		Gefahr
		
#. Einloggen auf CX mit Remotedesktop
#. Netzwerkverbindungstyp von Public nach Privat ändern	``network and sharing center -> choose homegroup and sharing options``
#. boxmaker_setup.zip runterladen und extrahieren
#. software installieren
	#. (optional) tortoiseSVN installieren
	#. node installieren (aktuell eingesetzte Version 4.2.3)
	#. prosody installieren (aktuell eingesetzte Version 0.9.7)
	#. nssm installieren / kopieren (aktuell eingesetzte Version 2.24)
#. software einrichten
	#. prosody
		#. prosody starten: :guilabel:`Start` -> :guilabel:`programme` -> :guilabel:`prosody`
		#. ``mod_auto_accept_subscriptions.lua`` aus aus boxmaker_setup.zip kopieren nach ``C:\Program Files\Prosody\plugins``
		#. ``prosody.cfg.lua`` aus boxmaker_setup.zip kopieren nach ``C:\Users\Administrator\AppData\Roaming\Prosody``
		#. copy \*.crt and \*.key to ``C:\Users\Administrator\AppData\Roaming\Prosody\certs``
		#. prosody neu starten
		#. benutzer anlegen. console starten:  :guilabel:`Start` -> :guilabel:`programme` -> :guilabel:`prosody` -> :guilabel:`telnet console`
		
		.. code:: html
		
			user:create("dab@horstm-boxmaker.de","dab")
			user:create("hmi@horstm-boxmaker.de","hmi")
			user:create("hmi2@horstm-boxmaker.de","hmi2")
			user:create("erpmng@horstm-boxmaker.de","erpmng")
			user:create("mediquc@horstm-boxmaker.de","mediquc")
	
		7. port in firewall öffnen: Control Panel\All Control Panel Items\Windows Firewall -> Advanced Settings -> Inbound Rules -> New Rule TCP-Port 5222 freigeben
