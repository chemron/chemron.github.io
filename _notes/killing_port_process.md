---
layout: post
title:  "Killing processes running on a port"
---

## The problem

Some process is using a port, preventing it from been used in other
applications. This could be from an error message such as:

```
Server started on port 3000  
Port 3000 is already in use
```

or

```
Address already in use - bind(2) for "127.0.0.1" port 3000 (Errno::EADDRINUSE)
```

## The solution

To solve this (at least on Linux/mac), first find the process id (PID) with the command:

```bash
lsof -i tcp:3000
```

and then kill the process with the command:

```bash
kill -9 [PID]
```

where `[PID]` is the given process id.
