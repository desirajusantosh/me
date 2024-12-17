---
title: "A Weekend Project: Reviving 2009 iMac - From El Capitan to Linux Mint"
weight: 2
resources:
params:
date: 2024-06-05T18:00:53-05:00
showDate: false
draft: false
tags: ["blog"]
---

### A Weekend Project: Reviving My 2009 iMac - From El Capitan to Linux Mint
This weekend turned into an unexpected tech adventure when I decided to breathe new life into my old iMac (2.66 GHz Intel Core 2 Duo, 8GB RAM, NVIDIA GeForce 9400 256MB). What started as a simple browser upgrade spiraled into a full system overhaul - and I learned quite a bit along the way.
The macOS Struggle
It all began with trying to get a modern browser running on OS X El Capitan. First hurdle? The Terms and Conditions screen that wouldn't budge. After some digging, I found a workaround - go back, skip the Apple ID setup, then return. Simple, yet not obvious. Then came the Homebrew saga. Hours spent watching terminal outputs like this:

bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"

Endless certificate errors, failed downloads, and progress bars that seemed frozen in time. El Capitan's age was showing - modern Homebrew just wasn't having it.
The Linux Mint Decision
After accepting that El Capitan was too outdated for modern web browsing, I decided to try Linux Mint. This meant diving into the depths of my house to find an old USB drive (found it buried in a drawer under a pile of old cables - we all have that drawer, right?). Enter Balena Etcher - the unsung hero of this story. Creating the bootable drive was surprisingly straightforward, though watching that progress bar felt like waiting for paint to dry.
The Great WiFi Adventure
Oh, the WiFi situation. Installing Broadcom drivers seemed simple enough:

bash
sudo apt-get update
sudo apt-get install --reinstall bcmwl-kernel-source

But no dice. Then came a parade of commands:

bash
sudo modprobe -r b43 bcma
sudo modprobe wl
sudo rfkill list all
sudo rfkill unblock all
sudo service network-manager restart

Still nothing. The breakthrough? An SMC reset - that magical combination of:

    Shutting down
    Unplugging the power cord
    Holding the power button for 30 seconds (feels like an eternity)
    Plugging back in and restarting

Suddenly, WiFi sprang to life. Sometimes the old "turn it off and on again" really is the answer!
The Dual-Boot Dream
Attempting to set up rEFInd for easy dual-booting:

bash
sudo ./refind-install

Each step was a mix of anticipation and mild anxiety - would this be the command that finally breaks something?
Looking Back
What started as a frustrated attempt to browse modern websites turned into a weekend of learning, troubleshooting, and ultimately succeeding. My trusty old iMac now runs both OS X El Capitan and Linux Mint, proving that sometimes limitations lead to better solutions. The machine that Apple had seemingly forgotten about now has a second life. Sure, it's not going to win any speed records, but it's perfectly capable of handling everyday tasks. Plus, there's something satisfying about keeping old hardware useful instead of adding to the e-waste pile. Next up? I'm thinking of exploring some lightweight Linux apps to really make the most of this setup. Maybe even set up a small home server? The possibilities are endless!
