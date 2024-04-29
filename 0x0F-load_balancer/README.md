0x0F. Load balancer
===================

-   Author: Sylvain Kalache, co-founder at Holberton School
-   Weight: 1


Key Ideas
--------

*In this project, students should focus on the following concepts:*

-   [Load balancer](https://alx-intranet.hbtn.io/concepts/46)
-   [Web stack debugging](https://alx-intranet.hbtn.io/concepts/68)

![](https://s3.amazonaws.com/intranet-projects-files/holbertonschool-sysadmin_devops/275/qfdked8.png)

Contextual Background
------------------

Two additional servers have been provided:

-   gc-[STUDENT_ID]-web-02-XXXXXXXXXX
-   gc-[STUDENT_ID]-lb-01-XXXXXXXXXX

The objective is to enhance the web stack to ensure redundancy for the web servers. This enhancement aims to handle more traffic by doubling the number of web servers and ensuring infrastructure reliability. Having a backup server enables seamless operation in case of failure of one server.

To achieve this, Bash scripts are required to automate the configuration process. These scripts must configure a new Ubuntu server to meet project specifications.

Resources
---------

**Recommended Reading or Viewing**:

-   [Introduction to load-balancing and HAproxy](https://alx-intranet.hbtn.io/rltoken/B7f3oz8i3Xvvom_YQZzLnQ "Introduction to load-balancing and HAproxy")
-   [Understanding HTTP headers](https://alx-intranet.hbtn.io/rltoken/sZ9v3Vq2tgLwN_PWVQketw "HTTP header")
-   [HAProxy packages for Debian/Ubuntu](https://alx-intranet.hbtn.io/rltoken/2VRAgtKKR9g6Xfb0xzGiSg "Debian/Ubuntu HAProxy packages")

Requirements
------------

### General

-   Permitted editors: `vi`, `vim`, `emacs`
-   Scripts to be interpreted on Ubuntu 16.04 LTS
-   All scripts should end with a new line
-   Mandatory presence of a `README.md` file at the root of the project folder
-   All Bash script files must be executable
-   Scripts must pass `Shellcheck` (version `0.3.7`) without errors
-   The first line of all Bash scripts must be `#!/usr/bin/env bash`
-   The second line of all Bash scripts must serve as a comment explaining the script's purpose

Server Configuration
------------

| Name | Username | IP | State |  |
| --- | --- | --- | --- | --- |
| 1733-web-01 | `ubuntu` | `3.235.21.36` | running |

Actions Toggle Dropdown

 |
| 1733-web-02 | `ubuntu` | `3.83.35.54` | running |

Actions Toggle Dropdown

 |
| 1733-lb-01 | `ubuntu` | `34.231.109.143` | running |

Actions Toggle Dropdown

 |

Tasks
-----

### 0\. Increase the number of webservers

mandatory

Score: 0.00% (Checks completed: 0.00%)

The initial task involves configuring `web-02` to mirror the configuration of `web-01`. Leveraging the Bash script developed during the [web server project](https://alx-intranet.hbtn.io/rltoken/-JluPVwfvXMOYMzNOqvgsQ "web server project") simplifies this process. Automation is preferred for efficiency.

Given that the web servers are placed behind a load balancer, a custom Nginx response header must be added. This header aids in tracking the web server handling HTTP requests, facilitating load balancer comprehension. More details on subsequent tasks.

Requirements:

-   Configure Nginx to include a custom header in its HTTP responses (on `web-01` and `web-02`)
    -   Custom HTTP header name: `X-Served-By`
    -   Value of the custom HTTP header: hostname of the Nginx server
-   Develop `0-custom_http_response_header` to configure a fresh Ubuntu machine as per task requirements
    -   [Ignore](https://alx-intranet.hbtn.io/rltoken/k3Bt6zu1On_-mDszxi0Z9w "Ignore") [SC2154](https://alx-intranet.hbtn.io/rltoken/9KwKHb9H8OJqcSK0saRIOA "SC2154") for `shellcheck`

Example:

```
sylvain@ubuntu$ curl -sI 34.198.248.145 | grep X-Served-By
X-Served-By: 03-web-01
sylvain@ubuntu$ curl -sI 54.89.38.100 | grep X-Served-By
X-Served-By: 03-web-02
sylvain@ubuntu$

```

Ensure proper configuration of server hostnames (`[STUDENT_ID]-web-01` and `[STUDENT_ID]-web-02`). Refer to this [tutorial](https://alx-intranet.hbtn.io/rltoken/tLVI0yDpGJXb-Op5Lo0JtQ "tutorial") if needed.

**Repo:**

-   GitHub repository: `alx-system_engineering-devops`
-   Directory: `0x0F-load_balancer`
-   File: `0-custom_http_response_header`

 

### 1\. Setup the load balancer

mandatory


Install and configure HAproxy on your `lb-01` server.

Requirements:

-   Configure HAproxy with version equal or greater than 1.5 to route traffic to `web-01` and `web-02`
-   Employ round-robin algorithm for request distribution
-   Ensure HAproxy can be managed via an init script
-   Confirm servers are configured with the correct hostnames: `[STUDENT_ID]-web-01` and `[STUDENT_ID]-web-02`. Refer to this [tutorial](https://alx-intranet.hbtn.io/rltoken/YkfzgEa6xNHrQbkKmJN4zg "tutorial") if necessary.
-   Provide a Bash script in your answer file to configure a new Ubuntu machine to meet the aforementioned requirements

Example:

```
sylvain@ubuntu$ curl -Is 54.210.47.110
HTTP/1.1 200 OK
Server: nginx/1.4.6 (Ubuntu)
Date: Mon, 27 Feb 2017 06:12:17 GMT
Content-Type: text/html
Content-Length: 30
Last-Modified: Tue, 21 Feb 2017 07:21:32 GMT
Connection: keep-alive
ETag: "58abea7c-1e"


X-Served-By: 03-web-01
Accept-Ranges: bytes

sylvain@ubuntu$ curl -Is 54.210.47.110
HTTP/1.1 200 OK
Server: nginx/1.4.6 (Ubuntu)
Date: Mon, 27 Feb 2017 06:12:19 GMT
Content-Type: text/html
Content-Length: 612
Last-Modified: Tue, 04 Mar 2014 11:46:45 GMT
Connection: keep-alive
ETag: "5315bd25-264"
X-Served-By: 03-web-02
Accept-Ranges: bytes

sylvain@ubuntu$

```

**Repo:**

-   GitHub repository: `alx-system_engineering-devops`
-   Directory: `0x0F-load_balancer`
-   File: `1-install_load_balancer`



### 2\. Puppetize custom HTTP header addition

#advanced

Similar to task #0, automate the creation of a custom HTTP header response, but with Puppet.

-   Custom HTTP header name: `X-Served-By`
-   Value of the custom HTTP header: hostname of the Nginx server
-   Develop `2-puppet_custom_http_response_header.pp` to configure a fresh Ubuntu machine as per task requirements

**Repo:**

-   GitHub repository: `alx-system_engineering-devops`
-   Directory: `0x0F-load_balancer`
-   File: `2-puppet_custom_http_response_header.pp`
