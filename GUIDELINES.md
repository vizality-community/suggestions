# Vizality Community Guidelines

### Preface

These guidelines are set to ensure Vizality's ecosystem stays as awesome as possible, and to avoid malicious plugins,
or plugins which affect the client's performance negatively. We will enforce **all** of these guidelines and take decisions we consider appropriate for plugins not complying with these guidelines. These guidelines will be enforced and, in most cases, be required to be met to have your plugin added to the repo officially. 

**Note**: We may decide, depending on the context, to let uncompliant plugins be added. These exceptions will be made at our sole discretion.

## The rules

Everything you build for Vizality should follow these rules:

### 1. Properly structure your plugin's manifest

All Vizality plugins require a valid `manifest.json` file.
This file is used internally to give information about the plugin to the end user, as well as define how the plugin
will behave. More info on this can be found in the documentation located [here](https://github.com/vizality/vizality-docs).

### 2. Follow Discord's terms of service

Even if Vizality is by nature against Discord's ToS (terms of service), it doesn't mean that you're allowed to do everything you want to. For example, collecting end user data without consent is forbidden.

### 3. No circumvention of Discord permissions

Do not circumvent Discord permissions or attempt to bypass anything restricted by the Discord client. This can
be a potential security breach or invasion of privacy (showing hidden channels, and storing deleted messages are both examples of invasion of user privacy).

### 4. Meet a certain standard performance wise

Plugins that are heavy in terms of resource usage are not great for user experience. Slower computers may not
be able to run Discord smoothly if your plugin is performing resource-heavy tasks. `MutationObserver` is an example of a generally resource-heavy method that should be avoided if possible.

If you do need to perform resource-heavy tasks, consider using a [web worker](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers).

### 5. Do not write harmful plugins

Harmful plugins that abuse Vizality's API or Discord's API or internals to do malicious things (including but not limited to
spam bots, keyloggers, scrapers, etc.) are strictly prohibited.

### 6. Respect user privacy

Collecting user data without consent is forbidden. All features that require the collection of user data
should be opt-in (if possible), and properly reflect data collection in your manifest with the `permissions` key (more info on this can be found in the documentation located [here](https://github.com/vizality/vizality-docs)).

### 7. Limit use of external APIs

External APIs, even open source, may secretly do malicious actions such as returning malicious data, logging your IP
address, and more. If you have to use your own API or another one that is not provided by a well-known entity (like Spotify
API), please add the `ext_api` permission to your manifest (more info on this can be found in the documentation located [here](https://github.com/vizality/vizality-docs)).

### 8. Avoid breaking other plugins

Your plugin should be able to run regardless of which other plugins the user has installed and enabled. We provide some protection internally to help with preventing conflicts, but you also need to do your part. If your plugin happens to be incompatible with another plugin, try to find a way to resolve it or try discussing possible solutions with the other plugin developer.

### 9. Prefer contributing instead of duplicating

If you want to make a plugin that already exists, consider contributing to the already existing plugin rather than having another
plugin with the same purpose. However, if you have radically different ideas or intentions, then by all means create your own.

### 10. Only perform manual HTTP requests to Discord if there are no other solutions

Discord's internal modules have mostly everything you'll need to retrieve data without directly calling the API or connecting to
the API gateway. Although unlikely, performing such actions may get user accounts flagged for self-botting or client modifying, which could result in an account ban.

### 11. Limit NSFW plugins

We're not against plugins providing NSFW features, but they should be properly labeled and handled. If your plugin can
provide NSFW content but it isn't its main purpose, **NSFW features must be turned off by default**. If the main feature of
the plugin is based on NSFW, please specify it in your manifest with the `nsfw` key (more info on this can be found in the documentation located [here](https://github.com/vizality/vizality-docs)), so that we can let users know.

## How we handle plugins

### Size doesn't matter

This is also true for plugins. Your plugin can be feature rich with thousands of lines of code, or just a few
lines. As long as they bring a new feature and follow the guidelines about, we will most likely accept it.

### You decide how to write your code

When reviewing plugins, we won't impose any specific code styles. Your code, your choices. We will, however, recommend some good practices (i.e. not mixing `"` and `'`), but we won't reject your plugin because of it.

### Do not attempt to bypass these guidelines

Anyone caught attempting to alter their plugin with intentions of bypassing these guidelines after being added to the repo shall be permanently banned from the repo and unable to have their plugins or themes added in the future.