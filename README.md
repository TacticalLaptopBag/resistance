# Resistance
This is a monorepo containing all divisions of Resistance.

Resistance is made to help you fight against porn.
You can add contacts, known as Squadmates, who will be notified if you are browsing the web for pornographic content.
Fighting alone is a losing war. Having a squad to help you will increase your chances of survival.

Be warned that this application may behave similarly to viruses. It's meant to be very difficult to remove or tamper with.

Currently, this massive project is a work-in-progress. Priorities are:
1. resistance-civil-protection, sending emails or using some other method to notify Squadmates should be simple to self-contain
2. resistance-scanner, monitoring web activity is the main feature that the user interacts with
3. resistance-overwatch, receiving data from Scanner will kick off functionality and will finally be alpha
4. resistance-airwatch, monitoring Overwatch and ensuring it doesn't go down will be a great protective barrier
5. resistance-cmacm, having a clean way to interface with all of this mess will land the project in beta
6. resistance-citadel, having a user-friendly way to interface with all of this will be even better, but isn't really all that necessary. This will likely just end up being a wrapper around CMACM.

## Why Resistance?
If you're on Windows or macOS, there are lots of tools to help fight porn addictions.
However, Linux has been left to dry, with many Linux users being forced to switch to Windows if they want to use monitoring software.
This solution won't be perfect, and there will likely be ways around it that I can't think of or solve. I'm only one guy.
However, it's a solution for Linux that exists, and doesn't need a server or subscription to use.
**Fighting porn together shouldn't cost you more than it already has.**
My hope is that this will help Linux users fight against porn.

## What About Local Content?
Resistance doesn't monitor downloaded content.
If you truly want to break free, you'll delete your downloaded stash of porn.

### Justification
Trying to monitor photos and videos that you are viewing is very difficult to do locally.
Covenant Eyes, a Windows/macOS/iOS/Android solution, does this by periodically taking screenshots,
blurring them, and sending them to a server to use a machine learning algorithm to determine if it should notify allies or not.
However, machine learning is very CPU expensive locally, and taking periodic screenshots is also significant processing.
I want Resistance to be friendly to laptops, so this is a problem.
Also, I don't want a server. I want this to be as accessible as possible.
It should be as simple as "Install and configure", or else the barrier will be too great.

Checking that you aren't going to any bad websites is much easier, and isn't a massive drain on battery either.
The only thing required is an internet connection to send emails, which is widely available, and is already present if you're visiting websites.

## Planned Features
Notifying Squadmates if...
- A website on the blocklist has been visited
- A search for pornographic content is made
- A web browser is not protected with Scanner
- The Squadmate config file has been tampered with outside of Civil Protection
- The Squadmate config file has been updated by Civil Protection
- Overwatch or Airwatch has been tampered with
- Overwatch or Airwatch was killed
- The user is attempting to remove any part of Resistance

Notifying Squadmates by...
- Email
- Text (need to know recipient's carrier)

Other features:
- Squadmates can only be removed by entering a verification code sent to the Squadmate
- Squadmates are notified when contact information for other Squadmates is changed

### Packaging
This likely won't be available as a Snap or Flatpak, as sandboxing would kneecap this project's capabilities.
I plan to at least make `.deb` and `.rpm` packages, to support any Debian-based or RHEL-based distros, which covers a lot of common distros,
such as Debian, Ubuntu, Mint, Pop!_OS, and Fedora, just to name a few.
Arch packages are a possibility, but depend on how much time I have and their complexity, as I've never packaged for Arch before.
If you're an Arch user, you've built packages before, you can build this one.
AppImages are iffy, I currently know very little of the format. I'll have to do more testing, but that is a low-priority task.

At the very least, a basic shell script installer will be available.
This script would install all the necessary build dependencies, clone this repo, build the project, and then install it.
This would make it difficult to update or remove, but it will work.

## Divisions

- [resistance-airwatch](https://github.com/TacticalLaptopBag/resistance-airwatch): Service to ensure Overwatch stays alive.
- [resistance-civil-protection](https://github.com/TacticalLaptopBag/resistance-civil-protection): Binary to help manage sending emails to Squadmates.
- [resistance-scanner](https://github.com/TacticalLaptopBag/resistance-scanner): Web browser extension to monitor activity and report to Overwatch.
- [resistance-overwatch](https://github.com/TacticalLaptopBag/resistance-overwatch): Service to monitor web browsers and receive information from Scanners.
- [resistance-cmacm](https://github.com/TacticalLaptopBag/resistance-cmacm): Combine Mainframe Access Command Module, a CLI interface to seamlessly interact with each of these systems.
Something that may also come: [resistance-citadel](https://github.com/TacticalLaptopBag/resistance-citadel), which would be the GUI frontend.

Yes, the names are Half-life 2 references.
They might not really make a lot of sense (Resistance is made up of Combine things?), but they just sound cool.
