{% unless site.data.devices[page.device].no_oem_unlock_switch %}
## Unlocking the bootloader

{% include note.html content="The steps below only need to be run once per device." %}
{% include warning.html content="Unlocking the bootloader will erase all data on your device!
Before proceeding, ensure the data you would like to retain is backed up to your PC and/or your Google account, or equivalent." %}

1. Visit [Xiaomi's website](https://global.account.xiaomi.com/pass/register) and create an account.
2. Start the phone, connect to the internet and enter the Mi account credentials into the phone `Settings` > `Accounts` > `Mi Account`
3. Enable developer options by `Settings` > `About phone` > and tapping `MUIU version` 7 times.
4. Link the device to your Mi account in `Settings` > `Additional settings` > `Developer options` > `Mi Unlock status` > `Add account and device`. This step is mandatory and will trigger a countdown of 72 hours, the waiting period before a device can be unlocked.
5. Optional: look if your phone is attached to the Mi account. Visit [Xiaomi's Mi site](https://i.mi.com) and sign in with `Mi account`. Open `find my device` and see if your device is listed.
6. After the waiting time visit [Xiaomi's official unlocking website](http://en.miui.com/unlock/) and download the Mi Unlock app (Windows is required to run the app, DON'T use a VM, the app will only work on a real machine).
7. After device and Mi account are successfully verified, the bootloader should be unlocked.
8. Since the device resets completely, you will need to re-enable USB debugging to continue.

{% include tip.html content="A Mi account is required to unlock devices, but beware that one account is only allowed to unlock one unique device every 30 days." %}
{% include tip.html content="It is highly recommended to have the latest official MIUI dev package installed on the device, before proceeding with unlock." %}
{% endunless %}

{% include templates/recovery_install_fastboot_generic.md %}
{% if site.data.devices[page.device].no_oem_unlock_switch %}
{% include tip.html content="It is highly recommended to have the latest official MIUI dev package installed on the device, before installing a custom recovery." %}
{% endif %}
