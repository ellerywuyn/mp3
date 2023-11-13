# Mini Project 3 – Designing a DSI Social Network Database in Neo4j

Author: Yuning Wu

## Quick navigation

[Database Design](#Database-Design)\
[Benefits and Challenges](#Benefits-and-Challenges)

## Database Design
### Node Types

1. **User Node**
   - Properties: UserID, VUNetID, Name, Email, ProfilePicture, CurrentRole, Bio, EnrollmentYear, GraduationYear, Employed, Company, Location, Job Position, Interests
   - Rationale: The foundation of any social network, representing all individuals on the platform. Properties like `StudentID`, `Name`, `Email`, `Bio` and `ProfilePicture` are standard across social networks. `CurrentRole`, `EnrollmentYear`, `GraduationYear`, `Employed`, `Company`, `Location`, `Job Position`, and `Interests` are tailored to create networking opportunities and professional connections.

2. **Post Node**
   - Properties: PostID, Content, Timestamp, MediaURL, LikesCount, CommentsCount, RepostsCount, ViewsCount, BookmarksCount, SharesCount, Topic, Type
   - Rationale: A central feature of social networks, allowing users to share information, thoughts, and media. Properties track engagement and reach (`LikesCount`, `CommentsCount`, `RepostsCount`, `ViewsCount`, `BookmarksCount`, `SharesCount`) and categorize content (`Topic`, `Type`), which is important for user experience and content discoverability.

3. **Community Node**
   - Properties: CommunityID, Name, Description, CreationDate, MemberCount, Category
   - Rationale: Reflects the community and subgroup aspect of the network, where users with similar interests or goals can congregate. Member count and category are particularly important for users to find relevant groups.

4. **Comment Node** 
   - Properties: CommentID, Content, Timestamp, MediaURL, LikesCount, CommentsCount, RepostsCount, ViewsCount, BookmarksCount, SharesCount, Type
   - Rationale: Enables interaction with content. By having properties similar to the Post node, comments themselves can be interacted with like posts, which is common in many social platforms that allow nested interactions.

### Edge Types

1. **Connection Edge** (User -> User)
   - Types: Friend, Colleague, Classmate, Professional
   - Properties: ConnectedSince
   - Rationale: Connects users to users, indicating when the connect was made and the type of connection. 

3. **Post Creation Edge** (User -> Post)
   - Properties: PostedAt, PostType (e.g., text, image, video)
   - Rationale: Connects users with their content, establishing ownership and context of posts.

4. **Comment Creation Edge** (User -> Comment)
   - Properties: CommentedAt, CommentType (e.g., text, image, video)
   - Rationale: Connects users to their comments, similar to post creation, indicating who commented and what type of comment was made.

5. **Comment Post Relation Edge** (Comment -> Post)
   - Properties: None
   - Rationale: Links comments directly to the posts they are related to, establishing a clear thread of conversation.

6. **Community Membership Edge** (User -> Group)
   - Properties: JoinedDate, Role (e.g., admin, member)
   - Rationale: Indicates which users are part of which groups and their roles within these groups, which is essential for managing access and interactions within groups.

## Benefits and Challenges

### Benefits

- **Networking Opportunities:** The inclusion of professional and academic properties within the User node facilitates networking among students and alumni.
  
- **Engagement Tracking:** The Post and Comment nodes' properties allow for a detailed analysis of user engagement and content performance.
  
- **Community Building:** Community nodes provide a space for like-minded individuals to connect and share ideas, strengthening the community.
  
- **Content Interaction:** The detailed Comment node enables rich interactions with content, potentially increasing platform stickiness.

### Challenges

- **Privacy Concerns:** With detailed user information, the platform must ensure data privacy and security.

- **Content Moderation:** High interaction capabilities mean the platform must have robust content moderation to prevent abuse.

- **Scalability:** As the platform grows, it will need to manage increasing data volumes and maintain performance.

- **User Engagement:** With many potential actions (likes, comments, shares, etc.), it's a challenge to keep users engaged and not overwhelmed.

