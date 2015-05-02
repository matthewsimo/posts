<!--
{
	  "title": "Initial Thoughts on Electron",
		  "tags": ["javascript", "code", "github", "electron"]
}
-->


Yesterday, I built and released [Obfus](https://github.com/tidbit/obfus) in just about an hour before work. I used it as an example app to play around with [Electron](http://electron.atom.io/), GitHub's tool to build cross platform desktop apps with web technologies. It runs some cool stuff ( Slack, Atom, etc.. ) and I've been geeking out for a chance to play.

I'd like to share my experiences and thoughts on how that went.


### Getting Started

Getting up and running with Electron was quite quick and painless. If you've got NPM installed it's as simple as:

```
npm install electron-prebuilt -g
```
The [Quick Start](https://github.com/atom/electron/blob/master/docs/tutorial/quick-start.md) guide was really helpful to get going quick, be sure and give it a once over.


### Building

Throwing together a quick app was a breeze, and should be just as nice for you if you're familiar with building with web technologies &amp; some basic knowledge of Node.js.

There were a couple of caveats that I ran into but sorted out promptly after referencing the [docs](https://github.com/atom/electron/tree/master/docs) - just keep this page open in a tab while you're starting out.

First, let's cover the cool things:

1. `web tech` - This is obvious, but it's really powerful when you dive in. All the benefits of quick releases, dev tools and debugging are still at your finger tips.
2. `docs` - As I stated previously the docs in the electron repo are pretty solid, the more advanced pieces (like packaging, distributing & deploying) are a little thin and should be updated with more details - but I'm sure that's coming.
3. `npm` - You have full access to all your favorite NPM modules, just use `require()` like normal.



And the minor hang ups:


1. `app.js` - While the docs are good, the actual application life cycle wasn't covered in depth ( though I understand why, it could dry and unnecessary overhead for quick onboarding ). `app.js` it doesn't have _too_ much to do with what you're actually building aside from bootstrapping your app and informing Electron of events it should watch out for and instructions on how it shold build the application window. Don't `console.log()` in here and look for stuff in dev tools, check the command line output.
2. `dev tools` - This is really minor but you can't right click to pull up the contextual menu to launch the dev tools.  Use the hotkey ( `alt+cmd+i` on Mac ) or the menu option to load them.
3. `large build size` - Obfus was just over 500KB unminified but when I went and followed the instructions on packaging my electron app for distribution it was 99 MB. This was a total bummer and sort of makes this not viable for clients or prime time. I did some brief digging on how to optimize the build and trim the fat but didn't dig anything up and had to get to work. In addition, this part of the docs needs the most work.   Clear instructions on optimizing your built app seems like it'd be crucial for people to actually adopt electron.

### Overall

Overall, I'm super excited for the possibility of using Electron more. It was fun to _actually_ build a desktop app, even if it was only a minor toy app. 

If you're a front-end engineer, don't feel limited in the native desktop space any longer. I'm sure it's only going to get better!

You can download Obfus [here](http://mas.im/ap1A) or check out the [source code](http://mas.im/aomv) to help you get started.



