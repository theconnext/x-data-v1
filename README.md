# x-data-v1
sample api endpoint for the demostration purpose


endpoint: /events/

GET /events/#{id}.json

```
{
name: "#{name}",
desc: "#{desc}",
cover: new URL(),
location: new Location(),
date: new Date(),
relations: {
  sessions:['#{sessionId}'],
  figure:{
    coordinater: ['#{figureId}'],
    speakers:['#{figureId}'],
    volunteer: ['#{figureId}'],
    supporting-teams: ['#{figureId}'],
    sponsor: ['#{figureId}'],
    other: ['#{other}'],
    }
  }
}
```

GET /figure/#{id}

```
{
uuid: ,//uuid
id: ,//memorizable Id
type: ,//enum[one,org]
name: ,// display name
bio: ,
link: {
  email: '#{emailAddress}', //validates email address
  avatar: "#{cdn}+#{imgID}" || avatarUrl || gravatar || default
  home: ,
  facebook: '#{gotoUrl}',
  weibo: '#{gotoUrl}'
}
relations: {
  hosters: [#{sessionUrl}]
  members: {
    owner: ["#{figureUrl}"],
    #{team}: ["#{figureUrl}"]
    }
}
}
```

```
GET /session/#{id}
{
uuid: ,
id: ,//unique id among all the sessions for all time and space.
type: enum[program,keynote,talk,rest],
topic: ,
desc: ,
duration: 15min,
relations: {
  next: {
    interlval: 5min,
    session: ["#{sessionUrl}"],
  sibling: ["#{sessionUrl}"],
  speaker: ["#{figureUrl}"],
  }
}
```
