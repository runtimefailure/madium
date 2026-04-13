---
description: >-
  Need assistance? We got you covered. This subpage covers all the current
  errors and solutions to what you may run into with Madium.
icon: hand-sparkles
---

# Support

### Dependencies

_Here are the required dependencies in order for_ [_<mark style="color:$primary;">**Madium**</mark>_](#user-content-fn-1)[^1] _to function properly._

* [Subscription on the Olemad channel.](https://youtube.com/@Olemad) (_required_)
* [.NET 8.0 x64](https://aka.ms/dotnet/8.0/windowsdesktop-runtime-win-x64.exe)
* [.NET 6.0 x64](https://aka.ms/dotnet/6.0/windowsdesktop-runtime-win-x64.exe)
* [VCRedist x86](https://aka.ms/vc14/vc_redist.x86.exe)
* [VCRedist x64](https://aka.ms/vc14/vc_redist.x64.exe)
* [Windows Desktop Runtime 3.1.32 x64](https://download.visualstudio.microsoft.com/download/pr/b92958c6-ae36-4efa-aafe-569fced953a5/1654639ef3b20eb576174c1cc200f33a/windowsdesktop-runtime-3.1.32-win-x64.exe)
* [VCRedist x86 (2013)](https://aka.ms/highdpimfc2013x86enu)
* [VCRedist x64 (2013)](https://aka.ms/highdpimfc2013x64enu)
* [VCRedist x86 (2012)](https://download.microsoft.com/download/1/6/B/16B06F60-3B20-4FF2-B699-5E9B7962F9AE/VSU_4/vcredist_x86.exe)
* [VCRedist x64 (2012)](https://download.microsoft.com/download/1/6/B/16B06F60-3B20-4FF2-B699-5E9B7962F9AE/VSU_4/vcredist_x64.exe)
* [VCRedist x86 (2010)](https://download.microsoft.com/download/1/6/5/165255E7-1014-4D0A-B094-B6A430A6BFFC/vcredist_x86.exe)
* [VCRedist x64 (2010)](https://download.microsoft.com/download/1/6/5/165255E7-1014-4D0A-B094-B6A430A6BFFC/vcredist_x64.exe)
* [VCRedist x86 (2008)](https://download.microsoft.com/download/5/D/8/5D8C65CB-C849-4025-8E95-C3966CAFD8AE/vcredist_x86.exe)
* [VCRedist x64 (2008)](https://download.microsoft.com/download/5/D/8/5D8C65CB-C849-4025-8E95-C3966CAFD8AE/vcredist_x64.exe)
* [.NET 6.0 Desktop Runtime v6.0.33 x64](https://builds.dotnet.microsoft.com/dotnet/WindowsDesktop/6.0.33/windowsdesktop-runtime-6.0.33-win-x64.exe)

### Bootstrappers

[_<mark style="color:$primary;">**Madium**</mark>_](#user-content-fn-1)[^1] _sometimes requires a custom launcher to properly stabilize Roblox during injection._

* [Fishstrap](https://github.com/fishstrap/fishstrap/releases/download/v2.9.1.2/Fishstrap-v2.9.1.2.exe) (_recommended_)
* [Bloxstrap](https://github.com/bloxstraplabs/bloxstrap/releases/download/v2.9.1/Bloxstrap-v2.9.1.exe) _(the starting point)_
* [VoidStrap ](https://github.com/voidstrap/Voidstrap/releases/download/v1.1.0.3/Voidstrap.exe)_(use at <mark style="color:$danger;">your</mark> own risk)_
* [FrostStrap](https://github.com/Meddsam/Froststrap/releases/download/v1.1.1.0/Froststrap-v1.1.1.0.exe) (for performance)

{% hint style="info" %}
Following bootstrappers are provided for [faq.md](faq.md "mention") (linux guide using winboat). If you are running Windows you can ignore thease.
{% endhint %}

* [Lution](https://lution.chip.is-a.dev/) _(for linux)_
* [Lucem](https://github.com/equinoxhq/lucem) _(for linux)_

### VPNs

_If you're experiencing issues with_ [_<mark style="color:$primary;">**Madium**</mark>_](#user-content-fn-1)[^1]_, a VPN can often resolve them instantly._

* [Cloudflare WARP](https://1111-releases.cloudflareclient.com/windows/Cloudflare_WARP_Release-x64.msi) _(free dns resolver)_
* [ProtonVPN](https://protonvpn.com/download/ProtonVPN_v4.3.13_x64.exe) (_recommended_)
* [Mullvad VPN](https://mullvad.net/en/download/installer/exe/latest) _(paid)_
* [Windscribe VPN](https://windscribe.com/install/desktop/windows) _(free)_

***

{% include ".gitbook/includes/roblox-version-mismatch-u....md" %}

This issue usually happens because your Roblox installation is outdated, or you're running an outdated version of Madium[^1].

{% hint style="info" %}
<mark style="color:blue;">**Note**</mark> When a version mismatch occurs, [_<mark style="color:$primary;">**Madium**</mark>_](#user-content-fn-1)[^1] displays the exact Roblox version you need inside its console. Use that version if you need to downgrade.
{% endhint %}

> Head over to [inject.today/rdd](https://inject.today/rdd) to download the latest [<mark style="color:$primary;">LIVE</mark> ](#user-content-fn-2)[^2]version of Roblox. Once you’ve got it, simply run the `launcher.exe` file to start Roblox and then re-attach. If you’re still experiencing issues, don’t worry just go to `%appdata%\Madium\Bin` and delete everything inside that folder. Then, grab a fresh copy of Madium from the [#download](https://discord.com/channels/1483453559692595252/1483497359748104344) channel or simply launch your bootstrapper to let it fully update Madium and then re-attach.

{% hint style="info" %}
<mark style="color:blue;">**Note**</mark> If you'd like to avoid re-downloading roblox with every update, you can use Roblox [#bootstrappers](support.md#bootstrappers "mention") such as Fishstrap as an example, simply head over to the deployment tab and switch the channel to [<mark style="color:$primary;">LIVE</mark>](#user-content-fn-2)[^2], as shown in the attached image below. It’s the simplest way to stay updated effortlessly! (also remember to change Automatic channel change action to Never chance because Roblox likes to change it sometimes)
{% endhint %}

<figure><img src=".gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

***

#### _Crash on Inject / Injection Timed Out_

{% hint style="info" %}
<mark style="color:blue;">**Note**</mark> If after doing everything provided inside of here Roblox still crashes, try to download [<mark style="color:$warning;">**BitDefender**</mark> ](https://www.bitdefender.com/en-pl/consumer/fragments/trial)[<mark style="color:$primary;">**Antivirus**</mark> ](#user-content-fn-3)[^3]trail and turning it off, doing so it will override other [<mark style="color:$primary;">**Antivirus**</mark> ](#user-content-fn-3)[^3]software so only it handles everything.
{% endhint %}

> Please follow all the steps outlined above. Make sure to exclude all Madium-related files from your antivirus software—they can be found at `%appdata%\Madium\Bin`. Before you start using Madium, it's a good idea to temporarily disable your antivirus to ensure everything runs smoothly. We're here to help you have a seamless experience! Also remember to download all the required [#dependencies](support.md#dependencies "mention") to prevent compatibility issues.

***

#### _Crash After X Minutes / DLL Disconnected_

> Please ensure all Madium files inside `%appdata%\Madium\Bin` are added to your Antivirus exclusion list. For the best experience, consider temporarily disabling your Antivirus software while using Madium to prevent any false flags or interruptions. If you're using a Roblox Bootstrapper, kindly make sure it’s also excluded from your Antivirus. This way, everything runs smoothly and without any hiccups!

***

#### _Update Failed (Check Connection)_

> Disable your antivirus software before launching the Madium bootstrapper.\
> Next, connect to a VPN—if you don’t have one yet, check out the [#vpns](support.md#vpns "mention") section above for some great options. Finally, relaunch the Madium bootstrapper and give it a moment to complete the update.

***

#### _Please set your preferred render mode to 'Direct3D 11' and relaunch_

{% hint style="info" %}
<mark style="color:blue;">**Note**</mark> You need to have DirectX Runtime installed in order to use this rendering mode in Roblox in order to download the runtime check out [#dependencies](support.md#dependencies "mention").
{% endhint %}

> Start your Roblox Bootstrapper (if you don't have one, take a look at [#bootstrappers](support.md#bootstrappers "mention")).\
> After launching click on configure settings, and once the settings window opens, go to the Engine Settings tab. Then, change the Rendering mode to Direct3D 11. After that, re-launch Roblox and Madium and your issue should be resolved.

***



#### _White/Blank/Empty interface, without any UI elements_

> The simplest way to resolve this issue is to make sure that you have all [#dependencies](support.md#dependencies "mention") installed, and once you have all of those installed go to `%localappdata%`  and delete both `com.madium.app`  as well as `com.madium.executor`  folders, once you've done all of these steps restart your device and re-launch Madium.



### Additional solutions

<details>

<summary>Open additional community fixes for crash and injection issues</summary>

> These fixes have helped some users with crash, injection, and DLL disconnect issues.
>
> They are <mark style="color:$warning;">not</mark> guaranteed fixes.
>
> Try the official steps on this page first.
>
> If needed, retry attach or inject a few times after each change.





#### _Basic cleanup steps_

These are simple fixes worth trying before deeper troubleshooting.

1. Update **Madium** to the latest version.
2. Update **Roblox Player** to the latest version.
3. If the issue continues, reinstall **Madium** and **Roblox**.
4. Press `Win + R`, type `%temp%`, and delete the files inside.
5. Empty the **Recycle Bin**.
6. Restart your PC.

#### _Disable potentially unwanted app blocking_

This setting can interfere with launching or injecting on some systems.

1. Open **Windows Security**.
2. Select **App & browser control**.
3. Open **Reputation-based protection settings**.
4. Find **Potentially unwanted app blocking**.
5. Turn off **Block apps**.

{% hint style="warning" %}
This option does not appear on every system.

Some Windows 10 and Windows 11 installs may not show it.
{% endhint %}

#### _Allow Madium through Windows Firewall_

This can help when Madium fails during launch, attach, or update checks.

1. Open **Windows Security**.
2. Select **Firewall & network protection**.
3. Click **Allow an app through firewall**.
4. Click **Allow another app**.
5. Add the `madium-launcher` file.
6. Make sure **Public** is enabled for the app entry.

#### _Lower CPU intensity limit_

Some users report better stability with a lower CPU intensity value.

1. Open **Madium**.
2. Go to **Settings**.
3. Find the CPU intensity option.
4. Set it to `90%`.

{% hint style="info" %}
This is a stability tweak.

It may reduce crashes for some users, but results can vary by system.
{% endhint %}

{% hint style="info" %}
If these fixes do not help, use the [Support Server](https://discord.gg/j2fPwe3Dqk) for more help.
{% endhint %}

</details>

***

### Missing Something?

> We’re always working to keep this page current with known issues and helpful solutions. If you don’t see your problem listed here, feel free to join our support server for live assistance—we’re happy to help!

{% hint style="info" %}
<mark style="color:blue;">**Note**</mark> Crashing related issues are entirely user related behavior therefore u cannot make a ticket regarding such issues. Same goes for version mismatches where the solution is inside of [#roblox-version-mismatch-unsupported-roblox-version](support.md#roblox-version-mismatch-unsupported-roblox-version "mention") section.
{% endhint %}

* [Support Server](https://discord.gg/j2fPwe3Dqk)

[^1]: The best free keyless Roblox Executor on the market as of the Velocity incident.

[^2]: Roblox production channel, where all users should have the same stable Roblox version.

[^3]: Software made to prevent running malicious programs.
