# Demo for yarn including .git folder with `yarn pack`

It includes empty `.git` folder in the `.tgz` file.

I would expect following to work (include package.json, README.md and lib directory with all subfiles), but it doesn't work at all:

    "files": [
        "lib",
        "README.md"
    ]

But unfortunately it doesn't. The best as was able to get is:


    "files": [
        "/lib/*",
        "/README.md"
    ]

But it includes empty `.git` directory and `.gitignore` for some reason...

See output below:

    $ yarn pack && tar xzvf yarn-git-v1.0.0.tgz
    yarn pack v0.17.3
    success Wrote tarball to "/Users/devoto13/Projects/yarn-git/yarn-git-v1.0.0.tgz".
    ✨  Done in 0.16s.
    x package
    x package/README.md
    x package/lib/code.js
    x package/.git
    x package/.gitignore
