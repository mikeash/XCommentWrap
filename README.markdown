# XCommentWrap

I like using single-line comment markers. I like hard-wrapping longer comments:

    // This thing does the thing and then afterwards
    // it does the other thing, which eventually
    // results in doing the last thing.

The result is nice but it's always a bit of a pain to type and maintain. I end up with a lot of inconsistent line lengths and changing text in the middle results in a lot of busy work.

This extension makes the computer do it for me, like it ought to. It hard wraps the selected lines to 80 characters, taking into account leading comment characters. It transforms this:

    // This thing does the thing
    // and
    // then afterwards it does the other thing, which eventually results in doing the last thing.

Into this:

    // This thing does the thing and then afterwards it does the other thing, which
    // eventually results in doing the last thing.

# How It Works

It doesn't have much in the way of smarts. It splits each line into a leading area and a trailing area, considering a leading area to be a sequence of spaces, tabs, `/`, and `*` characters. It then concatenates the trailing areas together with spaces in between and applies a hard wrap to the resulting string. Finally, it takes the leading area from the first line and prepends it to every line.

This means it will work on a bunch of single-line comments in sequence, whether they start with `//` or `///`. It will also work on multi-line comments provided your text is not on the same line as the initial comment indicator. It will not work on multi-line comments where the first line of text directly follows the `/*`. If you want that, you'll have to build it yourself.

# License

XCommentWrap is public domain. Do what you feel like with it. If you build something cool from it, credit would be nice, but not required. It's not like a huge amount of work went into it.
