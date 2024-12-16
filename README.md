# Dvorak – QWERTY ⌘ Suomi

This is a custom MacOS keyboard layout based on the Apple-provided Dvorak –
QWERTY ⌘ layout.
It accommodates my needs for an all-in-one keyboard layout.
My needs:

- Typing Finnish
- Typing Japanese and sometimes rōmaji
- Typing English
- Typing computer programs
- Wanting to use the Dvorak layout

## How does this layout differ?

This layout differs from standard Dvorak by:

- having ; replaced by ä
- having Shift-; still produce : (because it's such a common character when
  using a computer)
- having ä, ö, ; and : available behind a, o, ;, q (respectively), behind the
  Option key
- having å available behind Option-'
- having a macron (ō etc.) -producing dead key, produced by Option-D as an
  extension to the acute (á), two dots (ä), circumflex (â), grave (à) and tilde
  (ã) dead keys provided by the MacOS Dvorak layout.

## My JIS keyboard always produces some other alphabet layout having pressed the 英数/eisū key!?

This is unfortunate, but recent MacOSes consider custom keyboard layouts as
second class citizens and even as a security risk.
(A baseless accusation, in case of the declarative \*.keylayout format.)
They don't let your custom keyboard layout to take the place of a default
layout provided by the OS.

### Workaround 1: Installing a Japanese IME that lets you use a custom base layout

For example, [Google IME](https://www.google.com/inputtools/) and
[Kawasemi](https://monokakido.jp/ja/mac/kawasemi4/) let you use another
existing layout as a base layout.
If you use consistently the same IME for both alphabet and kana, the layout
handles mapping the 英数 and かな keys correctly, without changing back to the
OS alphabet layout.
I'm currently test-using Kawasemi, and it seems great.

### Workaround 2: Customizing the 英数 key functionality with Karabiner-Elements

You can fix this using
[Karabiner-Elements](https://karabiner-elements.pqrs.org/).
After installing it, add the following script as a "Complex modification"
script:

```
{
    "description": "Force Dvorak – QWERTY ⌘ Suomi on Eisu key",
    "manipulators": [
        {
            "from": { "key_code": "japanese_eisuu" },
            "to": [{ "select_input_source": {
              "input_source_id": "eu.drasa.keyboardlayout.dvorak_qwerty_suomi.dvorak–qwerty⌘suomi"
            }}],
            "type": "basic"
        }
    ]
}
```

## Why Dvorak – QWERTY ⌘?

Because many of the most common keyboard shortcuts such as Cmd-V and Cmd-X are
based on their location, not on a mnemonic.

Besides, I often feel like I'm using a different register in my brain to reach
for individual keys, as opposed to typing text continuously.
It helps to have the keys to correspond to their physically marked locations in
this case.

An aside: too bad that the handling of these shortcuts is broken in many
software programs.
Tells a lot about the general level of quality in software. I'll send patches
to fix things whenever I can.
