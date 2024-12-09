# dvorak_qwerty_suomi

This is a custom MacOS keyboard layout based on the Apple-provided Dvorak – QWERTY ⌘ layout. It accommodates my needs for an all-in-one keyboard layout. My needs:

- Typing Finnish
- Typing Japanese and sometimes rōmaji
- Typing English
- Typing computer programs
- Wanting to use the Dvorak layout

## How does this layout differ?

This layout differs from standard Dvorak by:
- having ; replaced by ä
- having ä, ö, : and ; available behind a, o, e, u, behind the Control key
- having ä, ö, : and ; available behind a, o, ä, q, behind the Option key
- having å available behind Option-'
- having a macron (ō etc.) -producing dead key, produced by Option-D as an extension to the acute (á), two dots (ä), circumflex (â), grave (à) and tilde (ã) dead keys provided by the MacOS Dvorak layout.

## My JIS keyboard always produces some other alphabet layout having pressed the 英数/eisū key!?

This is unfortunate, but recent MacOSes consider custom keyboard layouts as second class citizens and even as a security risk. (A baseless accusation, in case of the declarative *.keylayout format.) They don't let your custom keyboard layout to take the place of a default layout provided by the OS.

You can fix this using [Karabiner-Elements](https://karabiner-elements.pqrs.org/). After installing it, add the following script as a "Complex modification" script:

```
{
    "description": "Force Dvorak – QWERTY ⌘ Suomi on Eisu key",
    "manipulators": [
        {
            "from": { "key_code": "japanese_eisuu" },
            "to": [{ "select_input_source": { "input_source_id": "eu.drasa.keyboardlayout.dvorak_qwerty_suomi" }}],
            "type": "basic"
        }
    ]
}
```

## Why Dvorak QWERTY ⌘?

Because many of the most common keyboard shortcuts such as Cmd-V and Cmd-X are based on their location, not on a mnemonic.

Besides, I often feel like I'm using a different register in my brain to reach for individual keys, as opposed to typing text continuously. It helps to have the keys to correspond to their physically marked locations in this case.

An aside: Too bad that the handling of these shortcuts is broken in many software programs. Tells a lot about the general level of quality in software. I'll send patches to fix things whenever I can.
