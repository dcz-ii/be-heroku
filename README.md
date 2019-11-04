### GRAPHQL Queries For Meeting

## To-Do
- [ ] ScoreCard Table
- [x] Notes Table
- [ ] Rocks Table
- [ ] Todos Table
- [ ] Milestones Table
- [ ] Headlines Table
- [ ] IssuesList

# Delete All Data
```
mutation MyMutation {
  __typename
  delete_BasicsInfo(where: {Id: {_gt: 1}}) {
    affected_rows
  }
  delete_Meeting(where: {Id: {_gt: 1}}) {
    affected_rows
  }
  delete_CreatedByInfo(where: {Id: {_gt: 1}}) {
    affected_rows
  }
}
```

# Create Meeting

```
mutation CreateMeeting {
  insert_Meeting(objects: {Key: "string", MeetingToBasics: {data: {Name: "Meeting 1"}}, MeetingToCreatedByInfo: {data: {Name: "Created First"}}}) {
    affected_rows
  }
}
```

# Get Specific Meeting Data
```
query GetMeetingInfo {
  Meeting(where: {Id: {_eq: 44}}) {
    Id
    HeadlinesUrl
    HeadlineType
    CreateTime
    Key
    MeetingToBasics {
      Id
      Key
      Name
      TeamType
      Type
    }
    MeetingToCreatedByInfo {
      Id
      ImageUrl
      Key
      Name
      Type
    }
    MeetingType
    Type
  }
}
```

# Get All Meeting Data

```
query GetAllMeetingData {
  Meeting {
    Id
    HeadlinesUrl
    HeadlineType
    CreateTime
    Key
    MeetingToBasics {
      Id
      Key
      Name
      TeamType
      Type
    }
    MeetingToCreatedByInfo {
      Id
      ImageUrl
      Key
      Name
      Type
    }
    MeetingType
    Type
  }
}
```

# Create Attendees
```
mutation CreateAttendees {
  insert_Attendees(objects: {Name: "Fourth Name", meetingId: 44}) {
    affected_rows
  }
}
```