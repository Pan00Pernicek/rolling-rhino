# Rolling Rhino

Convert Ubuntu into a *"rolling release"* that tracks the `devel` series; **for the toughest of Ubuntu users**.

With custom patches for using in bedrock linux ubuntu stratum.

At moment these pactches are only for removing checks that are useless under bedrock configuration.

<h1 align="center">
  <img src=".github/logo.png" alt="Rolling Rhino" />
  <br />
  Rolling Rhino
</h1>

<p align="center"><b>Simple shell script to make Ubuntu track the `devel` series.</b></p>
<!-- <div align="center"><img src=".github/screenshot.png" alt="Rolling Rhino Screenshot" /></div> -->
<p align="center">Made with 💝 for <img src=".github/ubuntu.png" align="top" width="18" /></p>

## Introduction

Rolling Rhino is a simple tool to convert Ubuntu Desktop, and the official
desktop flavours, that has been installed from a daily image into a
*"rolling release"* by opting into and tracking the `devel` series.

Rolling Rhino is intended for Ubuntu developers and experienced Ubuntu users
who want to install Ubuntu once and the track all development updates with
automatic tracking of subsequent series.

We have a Discord for this project:

  * <https://discord.gg/DrQgYMf>

## Caveats

If you use Rolling Rhino to opt-in to `devel` series you're assuming support
of your system, including taking care of PPA migrations, cleaning
obsolete/orphaned packages and **actively participating in any issue resolution
for problems you may encounter** via [Launchpad](https://launchpad.net) using
tools such as `apport` and `ubuntu-bug`.

You will see `W: Conflicting distribution:` warnings from `apt` as its
configuration will now reference the `devel` series which is a pointer to the
current in-development series. But they are just that, warnings.

### Origins of Rolling Rhino

See here https://github.com/wimpysworld/rolling-rhino/blob/master/README.md

## Usage

  * Install Ubuntu to your bedrock system, using: `# brl fetch ubuntu`.
  * Boot the new install and use `rolling-rhino` to convert it to a rolling release.

```
git clone https://github.com/wimpysworld/rolling-rhino.git
cd rolling-rhino
strat -r ubuntu sudo ./rolling-rhino
```

Which will output something like this:

```
Rolling Rhino 🦏
  [+] INFO: No PPAs detected, this is good.
  [+] INFO: All checks passed.
Are you sure want to start tracking the devel series? [y/N]
```

## Credits
  * Thanks to [Wimpy's world](https://github.com/wimpysworld) for creating [rolling rhino](https://github.com/wimpysworld/rolling-rhino).
  * Thanks to [Stuart Langridge](https://twitter.com/sil) for [naming the project and proposing the idea]().
  * Thanks to [Sergio Schvezov](https://twitter.com/sergiusens) for [reminding me the `devel` series exists in Ubuntu](https://twitter.com/sergiusens/status/1276479711372292096).
  * Thanks to [RickAndTired](https://twitter.com/RickAndTired) for [answering the call for help](https://twitter.com/RickAndTired/status/1276729643068911618) and [making the Rolling Rhino logo](https://github.com/RickAndTired/Artwork).

## TODO

  - [x] Detect system is running an Ubuntu Development Branch.
  
  ~~- [x] Detect desktop meta packages.~~ (removed in this patch)
  - [x] Detect PPAs.
  - [x] Detect `sources.list` is not already tracking `devel`.
  - [x] Create clean `sources.list` that tracks `devel`.
  - [ ] Use `yad` to [create a UI](https://sanana.kiev.ua/index.php/yad)
