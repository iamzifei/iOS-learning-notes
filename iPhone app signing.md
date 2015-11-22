## iPhone app signing

The app must be *digitally signed* with your **Development Certificate**.

Apps that you want to submit to the App Store must be signed with **another** certificate, the **Distribution Certificate**.

In addition to a valid certificate, you also need a so-called **Provisioning Profile** for each app you make. Xcode uses this profile to sign the app for use on your device. *Provisioning Profile* is something for *app going on your device*.

The app's **Bundle Identifier**, or App ID, must be **unique**.