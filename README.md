# How to Containerize a .NET App with Docker With Visual Studio Code

### What You’ll Need
- **Docker Desktop**: Make sure you’ve installed the latest version.
- **Git**: You’ll need a Git client. Any client works, but the examples here use the command line.

---

### What’s This About?
This guide shows you how to:
1. Put a .NET app into a Docker container.
2. Run it !

---

### Step 1: Get the this Sample App
We’ll use a ready-made .NET app for this.

1. Open your terminal.
2. Go to the folder where you want to work.
3. Clone the app by running this command:

   ```bash
   git clone https://github.com/docker/docker-webapp-example
   ```

Now you have a folder called `docker-webapp-example`.

---

### Step 2: Set Up Docker Files
Docker needs some setup files to containerize your app. Thankfully, Docker makes this easy with the `docker init` command.

1. Go into the `docker-webapp-example` folder, can do this in your IDE too.
2. Run this in your terminal:

   ```bash
   docker init
   ```
   
   ![image](https://github.com/user-attachments/assets/f66f20fd-3681-4e9d-ae6b-65140b7b9092)

   

4. Answer a few questions:
   You will notice a prompt like thing in your terminal , if you click the up and down arrow on your keyboard , this will allow you to select a platform , then hit enter
   - **Platform**: Pick `ASP.NET Core`.
   - **Main Project**: Type `docker-webapp-example`.
   - **.NET Version**: Choose `9.0` or whichever version you have .
   - **Port**: Use `8080`, this can literally be any port number of your choosing.

   ![image](https://github.com/user-attachments/assets/c483510a-fb35-4505-8593-967993807c4c)


When done, Docker will create these files for you:
- `.dockerignore`
- `Dockerfile`
- `compose.yaml`
- `README.Docker.md`

![image](https://github.com/user-attachments/assets/da8bf2a0-999a-4635-87ba-bff4cc7cb0b2)


Your folder will now look like this:

```
docker-webapp-example/
├── docker-webapp-example/
├── .dockerignore
├── .gitignore
├── compose.yaml
├── docker-webapp-example.sln/
├── Dockerfile
├── README.Docker.md
├── README.md
```

---

### Step 3: Run Your App in Docker
1. In the `docker-dotnet-sample` folder, run this command:

   ```bash
   docker compose up --build
   ```
   
    ![image](https://github.com/user-attachments/assets/c11c18cc-9910-4f04-b332-25da4f5bf96d)
   
3. Head over to docker desktop and select the port as highlighted below. You’ll see the app running!

   ![image](https://github.com/user-attachments/assets/24297859-5dba-4ec6-b6c3-dd44b13af790)

   ![image](https://github.com/user-attachments/assets/80568a1b-e68c-423e-9479-90eeafbe11a2)


   
5. To stop the app, press `Ctrl+C` in the terminal, maybe twice to stop it in your IDE aswell.
   
   ![image](https://github.com/user-attachments/assets/80f33038-b271-4041-893f-606bb46040f7)

---

### Step 4: Run It in the Background (Optional)
Want the app to keep running even after you close the terminal? Do this:

1. Run:
   ```bash
   docker compose up --build -d
   ```
2. Check the app at [http://localhost:8080](http://localhost:8080).
3. To stop the app, run:
   ```bash
   docker compose down
   ```

---

### You Did It!
You just learned how to:
- Containerize a .NET app.
- Run it with Docker.

### Want to Learn More?
- [Dockerfile Basics](https://docs.docker.com/engine/reference/builder/)
- [.dockerignore File](https://docs.docker.com/engine/reference/builder/#dockerignore-file)
- [Docker Compose Guide](https://docs.docker.com/compose/)
```
