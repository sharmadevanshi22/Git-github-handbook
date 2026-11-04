<h5>Git & GitHub Cheat Sheet</h5>
<p>A beginner-friendly, practical reference to the most commonly used Git and GitHub commands, from creating your first repository to collaborating with a team.</p>

<br>

## Git Workflow

```mermaid
flowchart TD
    A["Working Directory<br/>Edit files"] -->|git add (git add "file_name") | B["Staging Area<br/>Stage changes"]
    B -->|git commit (git commit -m "Your message") | C["Local Repository<br/>Save changes"]
    C -->|git push (git push origin main) | D["Remote Repository<br/>GitHub"]

    style A fill:#dbeafe,stroke:#2563eb,color:#1e3a8a
    style B fill:#dcfce7,stroke:#16a34a,color:#14532d
    style C fill:#f3e8ff,stroke:#9333ea,color:#581c87
    style D fill:#ffedd5,stroke:#ea580c,color:#9a3412
```


<p>Created by Devanshi Sharma</p>

