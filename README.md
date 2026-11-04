# Tran-Duc-Duy/homebrew-tap

Homebrew tap for [NonSleep](https://github.com/Tran-Duc-Duy/nonsleep) — keeps a Mac awake with
the lid closed while AI coding agents run, and sleeps the moment they finish.

```sh
brew tap Tran-Duc-Duy/tap
brew trust Tran-Duc-Duy/tap          # Homebrew refuses casks from third-party taps until you do
brew install --cask nonsleep
```

Then click **Finish setup…** in the NonSleep window (or run `nonsleep setup`) once, to install the
sudoers rule that lets NonSleep toggle `pmset -a disablesleep 0|1`.

The app is ad-hoc signed, not notarized, so macOS asks for confirmation on first launch. Open it
once and allow it in *System Settings › Privacy & Security*, or run:

```sh
xattr -dr com.apple.quarantine /Applications/NonSleep.app
```

Updating and removal:

```sh
brew upgrade --cask nonsleep
brew uninstall --cask nonsleep   # restores normal sleep and removes the sudoers rule first
```

The cask is generated from the NonSleep repository (`Casks/nonsleep.rb` there, kept in sync with
`scripts/update-cask.sh vX.Y.Z`). Issues belong in the
[main repository](https://github.com/Tran-Duc-Duy/nonsleep/issues).
