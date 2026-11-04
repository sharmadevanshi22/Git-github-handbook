Git & GitHub Cheat Sheet

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=28&pause=1000&color=2F81F7&center=true&vCenter=true&width=850&lines=Git+%26+GitHub+Cheat+Sheet;Learn+Git+One+Command+at+a+Time;From+Beginner+to+Team+Collaboration" alt="Animated Git and GitHub heading" />
</p>

<p align="center">
  A beginner-friendly, practical reference to the most commonly used Git and GitHub commands — from creating your first repository to collaborating with a team.
</p>

<br>
 <B> Introduction </B>
<br>
Git is one of the most widely used version control systems in software development.
<br>
This cheat sheet is designed to help developers understand Git commands, manage repositories, track code changes, work with branches and collaborate using GitHub.
<br>
<B>
Who is this for? </B>
<br>
Beginners learning Git for the first time,
<br>
Developers working on individual projects,
<br>
Engineers collaborating with development teams,
<br>
Anyone preparing for technical interviews,
<br>

<b> What is Git? (The Tracking Tool) </b><br>

Git is a piece of software that runs locally on your own computer. It acts like a time machine for your project files<br>
• Tracks History: Every time you save your work (called a "commit"), Git takes a snapshot of your files. <br>
• Time Travel: If you make a mistake or break your code, you can easily roll back to a version that worked perfectly yesterday or last week.<br>
• Experiment Safely: You can create a copy of your project (called a "branch") to try out a new idea without messing up your main, working version. <br>

<b>What is GitHub? (The Online Hub)</b><br>

GitHub is a cloud-based website. It does not replace Git; it works with Git. <br>
• Cloud Storage: It hosts your Git projects (called "repositories" or "repos") online so you don't lose them if your computer crashes.<br>
• Teamwork: It allows multiple people to download the project, make their own changes using Git, and upload them back to the main project.<br>
• Open Source: It is a social network for developers where millions of people share their code publicly for anyone to use or improve.<br>


## Git Workflow

```mermaid
flowchart TD
    A["Working Directory<br/>Edit files"] -->|"git add filename"| B["Staging Area<br/>Stage changes"]
    B -->|"git commit -m 'Your message'"| C["Local Repository<br/>Save changes"]
    C -->|"git push origin main"| D["Remote Repository<br/>GitHub"]

    style A fill:#dbeafe,stroke:#2563eb,color:#1e3a8a
    style B fill:#dcfce7,stroke:#16a34a,color:#14532d
    style C fill:#f3e8ff,stroke:#9333ea,color:#581c87
    style D fill:#ffedd5,stroke:#ea580c,color:#9a3412
```

---



<p align="center">
  <b>⭐ If this cheat sheet helped you, consider giving this repository a star!</b>
</p>

<p align="center">
  Made with ❤️ by <b>Devanshi Sharma</b>
</p>

<p align="center">
  <i>Learn. Practice. Commit. Push. Repeat.</i>
</p>