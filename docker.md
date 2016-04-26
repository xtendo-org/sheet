```bash
docker build -t kinoru/dev .
docker run -d --name test_sshd -v /home/user/code:/home/user/code -v /home/user/Package:/home/user/package -v /home/user/...:/home/user/... -v /home/user/.vim:/home/user/.vim -h dev kinoru/dev
```

Clean up:

```bash
docker ps -a | sed 1d |  awk '{print $1}' | xargs docker r
```
