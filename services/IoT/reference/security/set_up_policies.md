---

copyright:
  years: 2015,2016

---

{:new_window: target="\_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Configuring security policies
{: #set_up_policies.md}
Last updated: 15 November 2016
{: .last-updated}

A security analyst can configure connection security policies and blacklists or whitelists.

## Configuring connection policies

You can set the default security level that is applied to all devices. You can then add custom security settings for specific devices.

1. On the Risk and Security Management add-on **Policies** page, click **Configure** beside **Connection Security**.
2. On the **Connection Security** page, select the default connection security level from the drop-down list. The value that you select here is applied to all devices, except for devices that have custom connection settings. These policies affect how the devices connect to the server -- they do not change any settings on the actual device or send any messages to the device. You can select one of the following security levels as the default:
    - TLS Optional
    - TLS with Token Authentication
    - TLS with Client Certificate Authentication
    - TLS with Token and Client Certificate Authentication

Based on the security level you select, the table shows the number of devices that are impacted, and the predicted level of compliance at the set security level.

3. If necessary, click **Add Custom Connection** and select the device types and custom security levels. The predicted compliance value is updated to reflect changes resulting from the custom security settings.
4. Click **Save**.  

## Configuring blacklists and whitelists

Restrict access to the server from certain devices by using a blacklist or use a whitelist to grant server access to specific devices. You an use either a blacklist or a whitelist -- they cannot be used together.

### Configure a blacklist

1. On the Risk and Security Management **Policies** page, in the **Blacklist** section, click **Configure**.
2. On the **Blacklist** page, click **Add to Blacklist**.
3. In the **Add to Blacklist** window, do one of the following:
    - On the **IP Address/Range** tab, enter the IP addresses devices that you want to block, or ranges of IP addresses for multiple consecutive devices.
    - On the **CIDR** tab, enter a Classless Inter-Domain Routing (CIDR) notated block.
    - On the **Country** tab, enter or select countries from which you want to block all devices.
4. In the **Add to Blacklist** window, click **Save**.
5. Review the list of blocked devices. Any devices that are a part of the list, based on IP address, CIDR, or country, are not able to connect to the Watson IoT Platform server.
6. Click **Save**.

### Configure a whitelist
1. On the Risk and Security Management **Policies**, click **Configure** beside **Whitelist**.
2. On the **Whitelist** page, click **Add to Whitelist**.
3. In the **Add to Whitelist** window, do one of the following:
    - On the **IP Address/Range** tab, enter the IP addresses devices that you want to allow access to, or ranges of IP addresses for multiple consecutive devices.
    - On the **CIDR** tab, enter a Classless Inter-Domain Routing (CIDR) notated block.
    - On the **Country** tab, enter or select countries from which you want to block access for all devices.
4. In the **Add to Whitelist** window, click **Save**.
5. Review the list of allowed devices. Any devices that are a part of the list, based on IP address, CIDR, or country, are  able to connect to the Watson IoTP server.
6. Click **Save**.
