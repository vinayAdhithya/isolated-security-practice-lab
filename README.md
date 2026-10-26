# Isolated Security Practice Lab

**Objective:** Establish safe, legal, reproducible conditions for beginner security testing.

**Target:** OWASP Juice Shop in Docker  
**Local URL:** http://127.0.0.1:3000  
**Estimated time:** 45–60 minutes

## 1. Prepare the environment
1. Install Docker Desktop (Windows/macOS) or Docker Engine (Linux) from its official source.
2. Create a folder named `isolated-security-practice-lab`.
3. Download the official Juice Shop image while connected to the internet:
   ```bash
   docker pull bkimminich/juice-shop
   ```
4. Do not configure router port forwarding, public tunnels, or remote access for this lab.

## 2. Start the isolated target
1. Save `compose.yaml` in this folder.
2. Run:
   ```bash
   docker compose up -d
   ```
3. Check the container:
   ```bash
   docker compose ps
   ```
4. On the same computer, open `http://127.0.0.1:3000`.
5. Keep the service bound to `127.0.0.1`; do not change it to `0.0.0.0`.

The image download requires network access, but the runtime service is published only on the host loopback interface and attached to a Docker network marked `internal: true`. Do not expose it through a router, tunnel, or public host.

## 3. Verify and document isolation
Run:
```bash
docker network inspect isolated-security-practice-lab_lab_net
docker compose ps
```
Capture genuine screenshots of:
- The browser showing `http://127.0.0.1:3000`.
- `docker compose ps` showing the target container is running.
- Network inspection showing `"Internal": true`.
- The topology diagram in `lab-topology.svg`.

Do not fake evidence. Avoid including passwords, tokens, or unrelated private information.

## 4. Practice within scope
Use only the local Juice Shop application and the permitted techniques in `rules-of-engagement.md`. Use fictional test data. Do not target the host operating system, other containers, other devices, public websites, or third-party services.

## 5. Stop and clean up
Stop the service:
```bash
docker compose down
```
If the lab is no longer needed, confirm its network is no longer in use before removing anything. Keep evidence and the completed ROE in this project folder.

## Evidence and one-link submission
Complete the evidence checklist in `evidence-checklist.md`, sign and date the ROE, and add the real screenshots. Put all files in one GitHub repository or one view-only shared folder. Set access to public or “anyone with the link can view,” then submit that single repository/folder URL.

**Note:** This package provides setup files and templates. The lab must still be run and the ROE personally signed before it can be represented as completed.
