---

copyright:
  years: 2015, 2016

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}


# Iniciación a {{site.data.keyword.GlobalizationPipeline_full}}
{: #globalizationpipeline}

*Última actualización: 6 de julio de 2016*
{: .last-updated}

{{site.data.keyword.GlobalizationPipeline_full}} es un servicio que proporciona la traducción automática y posibilidades de edición para traducir rápidamente interfaces de usuario web o móviles. Con su panel de control, la API RESTful y la integración con el conducto de entrega de la app, puede entregar a los clientes globales sin tener que volver a crear o desplegar la app.
{:shortdesc}

Puede utilizar el servicio {{site.data.keyword.GlobalizationPipeline_full}} con cualquier app en {{site.data.keyword.Bluemix}}, o no enlazado, por sí mismo. Puede crear, mantener y revisar traducciones rápidamente, con un esfuerzo mínimo y sin tener que salir de su entorno DevOps.

En la interfaz de {{site.data.keyword.GlobalizationPipeline_full}}, puede traducir rápidamente las app de {{site.data.keyword.Bluemix_notm}}. Para obtener información sobre la traducción de las apps utilizando la API RESTful, consulte [Referencia de API](https://gp-rest.ng.bluemix.net/translate/swagger/index.html){: new_window}. 


## Creación de un paquete
{: #globalizationpipeline_creatingbundles}

Con el servicio de {{site.data.keyword.GlobalizationPipeline_full}}, puede crear paquetes, que incluyen los archivos de recursos de las apps que se van a traducir. Los archivos de recursos pueden ser archivos Properties de Java, AMD I18N o JSON y deben tener contenido en la forma de pares clave/valor que representen las series de interfaz de usuario de la app. Para obtener más detalles y ejemplos de tipos de archivos soportados, consulte [Cómo trabajar con paquetes](./bundles.html){: new_window}.

Para crear un paquete, siga estos pasos:

1\. En el separador **Visión general**, pulse **Nuevo paquete**.

2\. Proporcione información sobre el paquete:

| Campo | Obligatorio| Descripción|
|-------|---------|------------|
| **ID del paquete** | Sí | Un nombre exclusivo para identificar el paquete. |
| **Idioma de origen** | Sí | El idioma nativo del archivo de origen. |
| **Archivo de recursos** | No | Un [archivo de recursos](bundles.html#globalizationpipeline_workingwithbundles) que se traducirá. El tamaño de archivo máximo está limitado a 2 MB. Los archivos de recursos especificados se subirán.  |
| **Formato de archivo** | No | El tipo de archivo que se está cargando. |
| **Idioma de destino** | No | Los idiomas para los que desea traducciones. |

**Nota:** Para cambiar el servicio de idiomas que proporciona la traducción automática para los paquetes, pulse el separador [**Configuración de MT**](./managing_translations.html#globalizationpipeline_service_to_service) para ver otros motores de traducción automática soportados.

3\. Pulse **Guardar**

Una vez que se haya creado el paquete, el archivo de recursos subido se traducirá a todos los idiomas de destino que haya especificado. El paquete nuevo se añade al separador Paquetes, donde puede:

* Añadir o eliminar idiomas
* Editar las traducciones generadas
* Actualizar el archivo de origen utilizado en el paquete y volver a generar las traducciones

## Importación de paquetes traducidos en el servicio
{: #globalizationpipeline_importtranslatedbundlesintoservice}

Como alternativa, si ya ha traducido archivos de recursos, puede importarlos a un paquete nuevo. Para obtener más información, consulte [Java Client Tools for {{site.data.keyword.GlobalizationPipeline_full}}](https://github.com/IBM-Bluemix/gp-java-tools).

**Nota:** si se actualiza el archivo de origen original, las claves y los valores definidos en el archivo se sincronizan con la versión más reciente del archivo de origen, de modo que solo se traducen los valores y las claves modificados.

## Estimación de uso de datos de {{site.data.keyword.GlobalizationPipeline_full}}
{: #globalizationpipeline_documentpricing}

{{site.data.keyword.GlobalizationPipeline_full}} almacena sus traducciones en una base de datos de fondo. Para calcular el tamaño de datos activo, puede hacer referencia a la fórmula siguiente:

`<expected resource data storage size in MB> ˜= 0.0005 * <number of key/value pairs in the source resource> * <number of languages including the source language>`

Según la fórmula, el tamaño de un paquete típico es `(longitud de clave + longitud del valor en UTF-8 = ˜40 bytes)`.

Por ejemplo, si tiene 100 pares clave/valor y los traduce a 9 idiomas, el tamaño de almacenamiento estimado es 0,0005 100 (9+1) = 0,5 MB. El tamaño real puede diferir en función del tamaño real de la clave/valor y de los metadatos almacenados junto con la traducción.

Utilice la [calculadora de tarifas](https://console.ng.bluemix.net/?direct=classic/#/pricing/cloudOEPaneId=pricing&paneId=pricingSheet&orgGuid=127a45f4-4461-4d5b-a26b-6dc2fdd1a3a2&spaceGuid=208fb1ff-413b-4fd9-9615-e8226062d0f3) de Bluemix para determinar los costes de servicio mensuales.


# Enlaces relacionados
{: #rellinks}
## Guías de aprendizaje y ejemplos
{: #samples}

* [Ejemplo Node.js](https://github.com/IBM-Bluemix/gp-nodejs-sample){: new_window}
* [Ejemplo Ruby](https://github.com/IBM-Bluemix/gp-ruby-sample){: new_window}

## SDK
{: #sdk}

* [Cliente Java](https://github.com/IBM-Bluemix/gp-java-client){: new_window}
* [Herramientas Java](https://github.com/IBM-Bluemix/gp-java-tools){: new_window}
* [Cliente JavaScript](https://github.com/IBM-Bluemix/gp-js-client){: new_window}
* [Cliente AngularJS](https://github.com/IBM-Bluemix/gp-angular-client){: new_window}
* [Cliente Ruby](https://github.com/IBM-Bluemix/gp-ruby-client){: new_window}
* [Cliente Python](https://github.com/IBM-Bluemix/gp-python-client){: new_window}

## Referencia de API
{: #api}

* [API RESTful de IBM Globalization Pipeline](https://gp-rest.ng.bluemix.net/translate/swagger/index.html){: new_window}

## Enlaces relacionados
{: #general}

* [Integrar Globalization Pipeline con Delivery Pipeline](https://hub.jazz.net/docs/deploy_ext/#globalize){: new_window}
* [Hoja de precios de IBM Bluemix](https://www.ng.bluemix.net/#/pricing){: new_window}
* [Requisitos previos de IBM Bluemix](https://developer.ibm.com/bluemix/support/#prereqs){: new_window}
