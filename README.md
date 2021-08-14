# Faceloader

A single binary to generate an ical file with multiple events linked from a Facebook page

## Why did we make FaceLoader?

Facebook has all but made it impossible for community groups to sync their data outside the platform. Where there was once multiple 'facebook to google cal' extensions and an open and easy-to-use API, now there's a big business only service that's been closed to new applications since the beginning of the Covid pandemic. Site crawling is actively discouraged through blocking requests from data centres and silently hiding future events for accounts that are not logged in. While there is a "download my data" option for personal pages, this is completely unsuitable for simple data sync of public data.

This is a pain in the butt for event promoters and community group organisers. Anyone who wants to both use Facebook to engage with an audience, and have this information to be available in other formats, currently only has the option of doing this manually with cut and paste. Facebook as an events platform has many desirable features such as easily allowing multiple event hosts, having events visible on more than one Page, and generally the social features that are really helpful for running an event.

### Our solution

While Facebook constantly shift the goalposts to stop easy interoperability, there is one thing they can't block: accessing the site as a logged in user to view your own events.

FaceLoader is a desktop app that takes the name of one or more Facebook pages and then pretends to be you by visiting each event link and downloading the data to your local computer. This creates a local copy on your computer you can cut and paste from into other event platforms, as well as an iCal feed you can sync with your Google or Outlook Calendar.

FaceLoader was designed primarily to be used with the PlaceCal event aggregation platform, which requires a public iCal feed or API to operate. We developed FaceLoader out of frustration with Facebook's insistance on making interoperability a total pain in the butt.

## Configuration

```shell
# set your page's url
echo 'FacebookPage: "https://www.facebook.com/myfacebookpage/events"' > config.yaml
# set the path to the chrome binary on your computer
echo 'ChromePath: "/usr/bin/chrome"' >> config.yaml
```

## Running

```shell
./faceloader > calendar.ics
```

## Development

Use [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) when writing your commit messages

To release, create and push a new tag and then run `goreleaser`