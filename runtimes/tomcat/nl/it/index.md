---

copyright:
  years: 2015, 2016

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}


# Tomcat
{: #tomcat_runtime}
Ultimo aggiornamento: 13 luglio 2016
{: .last-updated}

Il runtime Tomcat su {{site.data.keyword.Bluemix}} si avvale del java_buildpack.
{: shortdesc}

Per utilizzare il runtime Tomcat su {{site.data.keyword.Bluemix}}, devi specificare il java_buildpack con l'opzione -b. Ad esempio:
<pre>
    cf push &lt;myApp&gt; -p &lt;pathToMyApp&gt; -b java_buildpack
</pre>

Per ulteriori informazioni sul runtime Tomcat, consulta il
[java-buildpack readme](https://github.com/cloudfoundry/java-buildpack/blob/master/README.md).

## Applicazione starter
{: #starter_application}

{{site.data.keyword.Bluemix}} Fornisce un'applicazione starter Tomcat.  L'applicazione starter Tomcat è una semplice applicazione Python che fornisce un template che puoi utilizzare. Puoi fare delle prove con l'applicazione starter, apportare modifiche ed eseguirne il push all'ambiente Bluemix. Consulta [Utilizzo di applicazioni starter](../../cfapps/starter_app_usage.html) per informazioni sull'utilizzo dell'applicazione starter.

## Versioni di runtime
{: #runtime_versions}

Puoi modificare la versione di Tomcat che deve essere utilizzata dalla tua applicazione con la variabile di ambiente JBP_CONFIG_TOMCAT.
Puoi modificare la versione di Java che deve essere utilizzata dalla tua applicazione con la variabile di ambiente JBP_CONFIG_OPEN_JDK_JRE.
Possono essere entrambe specificate nel file manifest dell'applicazione.  Ad esempio:
```
    env:
        JBP_CONFIG_TOMCAT: '{tomcat: { version: 8.0.+ }}'
        JBP_CONFIG_OPEN_JDK_JRE: '{jre: { version: 1.7.0_+ }}'
```
{: codeblock}
La versione corrente del pacchetto di build è v3.6 che contiene Tomcat versione 8.30.0 e la versione Java predefinita 1.8.0_71.
Per ulteriori informazioni, consulta per favore le [java-buildpack releases](https://github.com/cloudfoundry/java-buildpack/releases).

# rellinks
{: #rellinks}
## general
{: #general}
* [java-buildpack](https://github.com/cloudfoundry/java-buildpack)
