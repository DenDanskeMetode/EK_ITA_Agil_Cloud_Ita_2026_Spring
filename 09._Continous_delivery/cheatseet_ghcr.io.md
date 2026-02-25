# GHCR.io cheatsheet


### **1. Log in to ghcr.io**
```bash
echo $GITHUB_TOKEN | docker login ghcr.io -u USERNAME --password-stdin
```
- Replace `USERNAME` with your GitHub username.
- Ensure you have a [GitHub Personal Access Token (PAT)](https://github.com/settings/tokens) with `read:packages`, `write:packages` and `delete:packages` scopes.

---

### **2. Pull an Image**
```bash
docker pull ghcr.io/OWNER/REPO:TAG
```
---

### **3. Push an Image**
```bash
docker tag LOCAL_IMAGE:TAG ghcr.io/OWNER/REPO:TAG
docker push ghcr.io/OWNER/REPO:TAG
```
- Tag your local image with the `ghcr.io` prefix before pushing.

---

### **4. List Images in a Repository**
```bash
curl -H "Authorization: Bearer $GITHUB_TOKEN" \
  "https://ghcr.io/v2/OWNER/REPO/tags/list"
```

---

### **5. Delete an Image**
```bash
curl -X DELETE -H "Authorization: Bearer $GITHUB_TOKEN" \
  "https://ghcr.io/v2/OWNER/REPO/manifests/DIGEST"
```
- Replace `DIGEST` with the image digest (find it using `docker inspect`).

---

### **6. Log Out**
```bash
docker logout ghcr.io
```

---
