# Portal Hack

After scanning with Nmap, Noya The Otter found open ports on the EJ Portal server, including one that provides a Linux shell!

EJ Portal lets teachers assign student grades, and since Noya did poorly on his H2 Math Promos, he wants help accessing the server at `challenge-services.ejctf-practice.xyz` via port `39001` to navigate the shell!

He promises if I change his grade, he'll reward me well... maybe I can get him to give me a flag?

## Summary
- **Topic:** Netcat/Linux
- **Category:** General Skills
- **Expected Difficulty:** Medium

## Hints
This challenge requires a Netcat connection, which you should have installed via nmap.

You can connect to any server via its port through this command: nc (server) (port)!

There will also be some Linux command knowledge tested, refer to this cheatsheet for your convenience: https://www.geeksforgeeks.org/linux-unix/linux-commands-cheat-sheet/

## Files
None

## Services
None
