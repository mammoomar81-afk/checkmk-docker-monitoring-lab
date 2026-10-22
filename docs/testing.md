# Test Documentation – Checkmk Docker Monitoring Lab

## 1. Test Objective

The objective is to verify that the Docker-based web server is accessible and that Checkmk detects service failures and recovery.

## 2. Test Environment

- Operating System: Ubuntu Server 22.04.5 LTS
- Monitoring: Checkmk Community 2.5.0p14
- Container Platform: Docker
- Web Server: Nginx
- Nginx URL: http://192.168.10.10:8080
- Checkmk URL: http://192.168.10.10:5000/gate/check_mk/

## 3. Test Cases

| Test | Action | Expected Result | Result |
|---|---|---|---|
| 1. Web access | Open the Nginx URL | Nginx welcome page is displayed | Passed |
| 2. HTTP response | Send an HTTP request to port 8080 | HTTP 200 OK | Passed |
| 3. Service failure | Stop the Nginx container | Checkmk reports a critical HTTP service | Passed |
| 4. Service recovery | Start the Nginx container again | Checkmk reports the HTTP service as OK | Passed |

## 4. Evidence

Screenshots documenting the tests are stored in the `screenshots/` directory.

- Nginx HTTP service overview
- HTTP service in CRIT state
- HTTP service recovered to OK

## 5. Conclusion

The tests demonstrate that the Nginx web server is accessible and that Checkmk detects a simulated service failure and its recovery.

These tests were performed in a local virtual lab environment.
