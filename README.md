# Mini Project 3 – Designing a DSI Social Network Database in Neo4j


## Quick navigation

[Database Design](#Database-Design)\
[Data](#data)\
[Models](#models)\
[Timeline](#timeline)\
[Repo Structure](#repo-structure)\
[Logistics](#project-logistics)\
[Resources](#resources)\
[Contact](#contact-info)


# Database Design
### Node Types

1. **User Node**
   - Properties: StudentID, Name, Email, ProfilePicture, CurrentRole, Bio, EnrollmentYear, GraduationYear, EmployedOrNot, Company, Location, Job Position, Interests

2. **Post Node**
   - Properties: PostID, Content, Timestamp, MediaURL, LikesCount, CommentsCount, RepostsCount, ViewsCount, BookmarksCount, SharesCount, Topic, Type

3. **Group Node**
   - Properties: GroupID, Name, Description, CreationDate, MemberCount, Category

4. **Comment Node** 
   - Properties: CommentID, Content, Timestamp, MediaURL, LikesCount, CommentsCount, RepostsCount, ViewsCount, BookmarksCount, SharesCount, Type

### Edge Types

1. **Friendship Edge** (User to User)
   - Properties: FriendshipSince, InteractionScore

2. **Post Creation Edge** (User to Post)
   - Properties: CreatedAt, PostType (e.g., text, image, video)

3. **Membership Edge** (User to Group)
   - Properties: JoinedDate, Role (e.g., admin, member)

4. **Attendance Edge** (User to Event)
   - Properties: RSVPStatus (e.g., going, interested, not going), RSVPDate

5. **Comment Edge** (User to Comment, and Comment to Post) (additional type for complexity)
   - Properties: CommentedAt

These nodes and edges are designed to represent a typical social networking structure where users can connect with each other, create and interact with posts, join groups, participate in events, and comment on posts. The properties chosen for each node and edge are meant to reflect the most common and essential attributes needed to capture the essence of the interactions on such a platform.
