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


## Database Design
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

1. **Post Creation Edge** (User -> Post)
   - Properties: PosteddAt, PostType (e.g., text, image, video)

2. **Comment Creation Edge** (User -> Comment)
   - Properties: CommentedAt, CommentType (e.g., text, image, video)

3. **Group Membership Edge** (User -> Group)
   - Properties: JoinedDate, Role (e.g., admin, member)

4. 

These nodes and edges are designed to represent a typical social networking structure where users can connect with each other, create and interact with posts, join groups, participate in events, and comment on posts. The properties chosen for each node and edge are meant to reflect the most common and essential attributes needed to capture the essence of the interactions on such a platform.
