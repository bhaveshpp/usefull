## Comman 

```
{
		"die coman": {
		"scope": "php,phtml",
		"prefix": "die",
		"body": [
			"die(__METHOD__.\"::\".__LINE__);",
		],
		"description": "die php"
	},
	"pre": {
		"scope": "php,phtml",
		"prefix": "pre",
		"body": [
			"echo \"<pre>\";",
			"print_r($1);",
		],
		"description": "print r php"
	}
}

```

## Magento

```
{
	"code for module.xml of module": {
		"scope": "",
		"prefix": "module.xml",
		"body": [
			"<?xml version='1.0'?>",
			"<config xmlns:xsi='http://www.w3.org/2001/XMLSchema-instance' xsi:noNamespaceSchemaLocation='urn:magento:framework:Module/etc/module.xsd'>",
			"   <module name='$1' setup_version='$2'></module>",
			"</config>"
		],
		"description": "mecro for Module.xml"
	},
	"code for registration.php of module": {
		"scope": "",
		"prefix": "registration.php",
		"body": [
            "<?php",
			"use Magento\\Framework\\Component\\ComponentRegistrar;",
            "ComponentRegistrar::register(",
            "\tComponentRegistrar::MODULE,",
            "\t'$1',",
            "\t__DIR__",
            ");"
		],
		"description": "macro for registration.php"
	},
	"code for composer.json of module": {
		"scope": "",
		"prefix": "composer.json",
		"body": [
            "{",
            "    \"name\": \"${1:bhaveshpp}/${2:modulename}\",",
            "    \"description\": \"${3:Discription}\",",
            "    \"type\": \"magento2-module\",",
            "    \"version\": \"1.0.0\",",
            "    \"minimum-stability\": \"dev\",",
            "    \"prefer-stable\": true,",
            "    \"license\": [",
            "        \"OSL-3.0\",",
            "        \"AFL-3.0\"",
            "    ],",
            "    \"require\": ",
            "    {",
            "        \"php\": \">${4:7.0}\"",
            "    },",
            "    \"autoload\": ",
            "    {",
            "        \"files\": ",
            "        [ ",
            "            \"registration.php\" ",
            "        ],",
            "        \"psr-4\": ",
            "        {",
			"            \"${5:Bhaveshpp\\\\\\ModuleName}\": \"\"",
            "        }",
            "    },",
            "    \"authors\": [",
            "        {",
            "          \"name\": \"Bhavesh Prajapati\",",
            "          \"email\": \"bhaveshp.magento@gmail.com\",",
            "          \"role\": \"Developer\"",
            "        }",
            "    ]",
            "}"
        ],
		"description": "macro for composer.json"
	},
	"NOTICE OF LICENSE": {
		"scope": "",
		"prefix": "comment",
		"body": [
			"/**",
			" * Bhaveshpp ",
			" *",
			" * This code is developed by Bhavesh Prajapati",
			" *",
			" * Do not edit or add to this file if you wish to upgrade this extension to newer",
			" * version in the future.",
			" *",
			" * @authors https://github.com/bhaveshpp",
			" */"
		],
		"description": "macro for comment"
	},
	"menu.xml": {
		"scope": "",
		"prefix": "menu.xml",
		"body": [
			"<?xml version=\"1.0\"?>",
			"<config xmlns:xsi = \"http://www.w3.org/2001/XMLSchema-instance\" xsi:noNamespaceSchemaLocation = \"urn:magento:module:Magento_Backend:etc/menu.xsd\">",
			"    <menu>",
			"        <add ",
			"            id = \"${1:Bhaveshpp_Module}::${2:id}\" ",
			"            title = \"${3:Title}\" ",
			"            module = \"${1:Bhaveshpp_Module}\" ",
			"            sortOrder = \"$4\" ",
			"            resource = \"${1:Bhaveshpp_Module}::${5:id}\" ",
			"            parent = \"${1:Bhaveshpp_Module}::${6:id}\"",
			"        />",
			"        <add ",
			"            id = \"${1:Bhaveshpp_Module}::${7:id}\" ",
			"            title = \"${8:Title}\" ",
			"            module = \"${1:Bhaveshpp_Module}\" ",
			"            sortOrder = \"$9\" ",
			"            action = \"${10:admin_routes/path}\" ",
			"            resource = \"${1:Bhaveshpp_Module}::${11:id}\" ",
			"            parent = \"${1:Bhaveshpp_Module}::${12:id}\"",
			"        />",
			"    </menu>",
			"</config>"
		],
		"description": "macro for admin menu"
	},
	"routes.xml": {
		"scope": "",
		"prefix": "routes.xml",
		"body": [
			"<?xml version = \"1.0\"?>",
			"<config xmlns:xsi = \"http://www.w3.org/2001/XMLSchema-instance\" xsi:noNamespaceSchemaLocation = \"urn:magento:framework:App/etc/routes.xsd\">",
			"    <router id = \"admin/standard\">",
			"        <route id = \"${1:routes_id}\" frontName = \"${1:routes_id}\">",
			"            <module name=\"${2:Bhaveshpp_Module}\"/>",
			"        </route>",
			"    </router>",
			"</config>"
		],
		"description": "macro for routes"
	},
	"di.xml": {
		"scope": "",
		"prefix": "di.xml",
		"body": [
			"<?xml version = \"1.0\"?>",
			"<config xmlns:xsi = \"http://www.w3.org/2001/XMLSchema-instance\" xsi:noNamespaceSchemaLocation = \"urn:magento:framework:ObjectManager/etc/config.xsd\">",
			"    <preference for=\"Blackbird\\Monetico\\Controller\\Onepage\\Success\" type=\"Bhaveshpp\\Custom\\Overwrite\"/>",
			"    <type name=\"Magento\\AdvancedSearch\\Block\\SearchData\">",
			"         <plugin name=\"BeforeFormatDate\" type=\"Bhaveshpp\\Custom\\Overwrite\" sortOrder=\"1\" />",
			"    </type>",	
			"</config>"
		],
		"description": "macro for di"
	},
	"system.xml": {
		"scope": "",
		"prefix": "system.xml",
		"body": [
			"<?xml version = \"1.0\"?>",
			"<config xmlns:xsi = \"http://www.w3.org/2001/XMLSchema-instance\" xsi:noNamespaceSchemaLocation = \"urn:magento:module:Magento_Config:etc/system_file.xsd\">",
			"\t<system>",
			"\t\t<tab id=\"bhaveshpp\" translate=\"label\" sortOrder=\"100\">",
			"\t\t\t<label>Bhaveshpp</label>",
			"\t\t</tab>",
			"\t\t<section id=\"blogpost_setting\" translate=\"label\" sortOrder=\"100\" showInDefault=\"1\" showInWebsite=\"1\" showInStore=\"1\">",
			"\t\t\t<class>separator-top</class>",
            "\t\t\t<label>Blogpost</label>",
            "\t\t\t<tab>bhaveshpp</tab>",
			"\t\t\t<resource>Bhaveshpp_Blogpost::setting_configuration</resource>",
            "\t\t\t<group id=\"general\" translate=\"label\" type=\"text\" sortOrder=\"1\" showInDefault=\"1\" showInWebsite=\"0\" showInStore=\"0\">",
            "\t\t\t\t<label>General Configuration</label>",    
            "\t\t\t\t<field id=\"enable\" translate=\"label\" type=\"select\" sortOrder=\"1\" showInDefault=\"1\" showInWebsite=\"1\" showInStore=\"1\">",
            "\t\t\t\t\t<label>Enable</label>",
            "\t\t\t\t\t<source_model>Magento\\Config\\Model\\Config\\Source\\Yesno</source_model>",
            "\t\t\t\t</field>",
            "\t\t\t</group>",
        	"\t\t</section>",
    		"\t</system>",
 			"</config>"
		],
		"description": "macro for routes"
	}

}


```

