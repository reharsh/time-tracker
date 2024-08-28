# time-tracker

Simple Next JS application to track study time wrt to the subjects along with the todos of each subject refer to the below diagrams.

## Tech Stacks to be used

- Front-end: NextJS with app router, Tailwind, Axios
- Back-end: Next API Routes/Route Handlers
- Misc: Recoil, Zod
- Authentication: NextAuth (Google only) (you can use Supabase Authentication if you want)
- Database: Supabase DB, Prisma/Drizzle as ORM
- File Storage: Use Supabase storage to store captured images.
- Deployment: Vercel and Docker

  
## Screens with Routes

### landing page:
  - route: '/'
  - desc: cool saas landing page with proper use of component libraries.
<img width="728" alt="image" src="https://github.com/user-attachments/assets/7c01d922-d45c-430f-a866-187c06e16282">

### login page:
  - route: '/login'
  - desc: simple login page built using NextAuth (Implement Google Login only for now)
<img width="643" alt="image" src="https://github.com/user-attachments/assets/614ef416-8b99-4c07-9dc7-ff7469a01754">

### home page:
  - route: '/home'
  - desc: home page with total productive time and different subjects with their time.
<img width="643" alt="image" src="https://github.com/user-attachments/assets/148fcbe2-cf52-45c1-a1f5-b2f8110964e8">

### create subject:
  - route: '/createsubject'
  - desc: simple subject name as input to create a new subject
<img width="650" alt="image" src="https://github.com/user-attachments/assets/faa6ea17-7216-4e7d-a158-eb329749fae6">


### subject page:
  - route: '/subject1'
  - desc: This is a subject-specific dynamic route with total time + break time for that subject along with todos associated with that subject
<img width="643" alt="image" src="https://github.com/user-attachments/assets/9bb07c65-7781-4e84-a583-c9ddd9009843">

### Capture
  - route: '/subject1' (same as subject route)
  - desc: utilize camera web API to access the user's camera in the browser and capture the photo.
    <img width="650" alt="image" src="https://github.com/user-attachments/assets/2c3b34fb-b2df-431d-b4a2-15f4836bfa69">

## Schemas

These are just **suggestions** for schemas of Subject and Task, you can implement these according to yourself.

```
subject {
    time: (string),
    breakTime: (string),
    createdAt: (date/time),
    completedAt: (date/time),
    tasks: [task]
}
```
```
task{
    content: (string)
    isCompleted: (boolean)
    imgURL: ""
    createdAt: (date/time)
    completedAt: (date/time)
}
```

**Note**: Flow of capturing the Image for each task completion is as follows
- click on any task to mark it completed
- camera will be opened
- use camera web api to capture images (or any library compatible with NextJs)
- upload image to supabase storage and get URL of image
- update this task's entry as completed into db with imgURL recieved from supabse

  **DO ANYTHING IN ANY WAY, ONLY FUNCTIONALITY OF WEB APP MATTERS**

