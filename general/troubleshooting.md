# Troubleshooting

Ran into a problem? This section may have the answers.. or not.

![Info: ](../assets/images/icons/icon_info.png) If there is something you are having trouble with and didn't find it here, please raise an enquiry at the [**Discord server**](https://discord.gg/UzrMtCD7y9) for **Pandora's box**. That is where it is most likely to be noticed.

### The editor crashed

Please raise a bug report to the development *Discord* as indicated above, to the `#editor-feedback` channel. Be sure to include the reproduction scenario, and if possible also a screenshot of the details of the error so that I may investigate.

### The game crashes with burnt chicken

This usually happens when there is a bad configuration that attempts to access invalid data (it was deleted/renamed/set incorrectly).

It can also happen when values are set to fields which the game does not expect. e.g an invalid enumeration value is set to a field. The field accepts a range of 0 to 5, but you put 6.

To get a hint of what might be wrong, you will need to learn how to interpret the game's crash dump. It will usually contain a function call stack, with a clue indicating what went wrong. (No examples available at this time)

### The game crashes with no error

Bad configurations can sometimes cause this. You'll need to roll-back to an earlier version of your mod. Did you [use Git](./getting-started.md#use-git)? If not, I strongly recommend learning how.

### The application was detected as a virus

I'm afraid there isn't much I can do about this one. The true solution is to get the tool's executable code-signed, but I cannot afford it because it costs hundreds of USD a year to subscribe to a signing certificate. You could try using a different computer, or a virtual machine.