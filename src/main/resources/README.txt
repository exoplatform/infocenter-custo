****************************
* How to edit this project *
****************************

1/ Project name
---------------

Pay attention to the name you give to this project.
It defines the name of the jar, this nameis  used by the Eclipse Help Center to find the resources in this project.

Currently, it is: org.exoplatform.doc.style


2/ plugin.xml
-------------

Here is quickly explained the structure and important information about the plugin.xml file:

<plugin>
   <extension
         id="default"									// Important, the name of the customization extension
         name="Default Style"
         point="org.eclipse.core.runtime.products">		// What to customize. You shouldn't have to change this
      <product
            application="default"
            name="eXo Platform Documentation">			// The title of the help center, as seen in the browser
         <property
               name="preferenceCustomization"			// The variable and
               value="exo.ini">							// the name of the customization preferences
         </property>
      </product>
   </extension>
</plugin>


Resources:
* http://help.eclipse.org/helios/topic/org.eclipse.platform.doc.isv/guide/ua_help_war.htm
* http://help.eclipse.org/helios/topic/org.eclipse.platform.doc.isv/guide/ua_help_infocenter_preferences.htm
* http://help.eclipse.org/helios/topic/org.eclipse.platform.doc.isv/guide/ua_help_setup_preindex.htm
* http://blog.maxant.co.uk/pebble/2008/06/09/1213043100000.html


3/ exo.ini
----------

All the preferences are detailed in:
http://help.eclipse.org/helios/topic/org.eclipse.platform.doc.isv/guide/ua_help_setup_preferences.htm

Resources:
* http://help.eclipse.org/helios/topic/org.eclipse.platform.doc.isv/guide/ua_help_setup_preferences.htm
* http://help.eclipse.org/helios/topic/org.eclipse.platform.doc.isv/guide/ua_help_setup_about.htm


4/ Activate your customization project
--------------------------------------

Your customization project needs to be activated in the Eclipse Help Center configuration.
As explained at the bottom of http://help.eclipse.org/helios/topic/org.eclipse.platform.doc.isv/guide/ua_help_war.htm

"If you look in the config.ini in the help.war file under directory help/WEB_INF/configuration you will notice the
line eclipse.product=org.eclipse.productname. If your product has help system customizations in a product plugin you can
activate these by changing this line to point to your product plugin."

The value of the eclipse.product variable is formed as follows: {project name}.{extension name}

Currently, it is: org.exoplatform.doc.style.default
                  {     project name      }.{extension name}

By default, this variable is disabled in the Eclipse Help Center war archive.
