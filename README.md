# Cork Cat Club 
The guide for adding and removing shows from cork cat club are outlined here. 

## Adding a show

I'll go through each of these steps below, but in order to get a new show on the website, the following 
seven steps must be followed:

1. Gather the required information for the show (name, date, location, etc)
2. Upload the relevant files (e.g. entry forms, rules, etc) to Dropbox
3. Put the show information into the format required by the website
4. Log into CCC's Github repo
5. Paste the information into the shows file, and save the changes
6. The website should be automatically updated about 5 minutes after the file is saved
7. Check that the new page is accuract - visit the page, check the entered information, make sure the 
   files can be downloaded. 
   

## Adding an example competition

The show information must be put together in a slightly strange format that the website understands. I'll go
through each field that is needed individually

### Competition name
For the sake of this example, let's imagine there's a show called "Cat Competition".

### Date and time
This imaginary competition takes place on the 14th of April 2021 between 11 in the morning to 3 in the 
afternoon. This date information needs to be added in `yyyy-mm-dd` format, that is `2021-04-21` and the 
times in 24-hour format, that it it starts at `11:00` and ends at `15:00`. The website needs the date and time
combined into one string with a `T` separating them. For the start, therefore, the date-time is `
2021-04-14T11:00` and the end is `2021-04-14T15:00`. 

### Location and address 
We're going to imagine that it happens in "City Hall". I'll use Google Maps to get the address for Cork City 
Hall, which gives `City Hall, Anglesea St, Centre, Cork, Ireland`. Keep the Google Maps page open, because you
need to get the latitude and longitude of the location from this too. The URL I get after searching looks like 
this:

> https://www.google.com/maps/place/Cork+City+Council,+City+Hall/@51.8971356,-8.4676703,17z

The first number (`51.8971356`) is the latitude, and the second (`-8.4676703`) is the longitude. 

### Entry forms
Let's imagine this competition has two entry forms, one for pedigree and the other for non-pedigree entrants. 
Upload these to Dropbox and keep the links to these on hand. You can add as many links as are needed. For this 
imaginary competition, the URLs are `https://www.dropbox.com/pedigree-entry-form.pdf` and 
`https://www.dropbox.com/non-pedigree-entry-form.pdf` respectively. 

### Putting it all together
All of this information must be combined into the following structure. It might look a little unusual, but it's 
what the website expects. A little care must be taken with the start and end fields since it's a combination of the
date and the time with a `T` between. 

```yaml
- name: "Cat Competition"
  start: 2021-04-14T11:00
  end: 2021-04-14T15:00
  location: "Cork City Hall"
  address: "City Hall, Anglesea St, Centre, Cork, Ireland"
  latitude: 51.8971356
  longitude: -8.4676703
  urls:
    - name: "Pedigree entry form"
      url: "https://www.dropbox.com/pedigree-entry-form.pdf"
    - name: "Non-pedigree entry form"
      url: "https://www.dropbox.com/non-pedigree-entry-form.pdf"
```

## Adding an entry
First, make sure you are logged into CCC's Github account. Then copy the data that has been put together, and go
to this webpage

> https://github.com/njtwomey/cork-cat-club/edit/gh-pages/_data/shows.yaml

Once there, and paste the information to the top of the file, and click on "Commit Changes". In a few minutes the 
changes will be live on `https://corkcatclub.net/shows/schedule`

## Removing an entry 
First, make sure you are logged into CCC's Github account. Go go to this webpage

> https://github.com/njtwomey/cork-cat-club/edit/gh-pages/_data/shows.yaml

Find the lines that correspond to the show that you want to remove, and delete them from the file. In a few minutes 
the changes will be live on `https://corkcatclub.net/shows/schedule`
