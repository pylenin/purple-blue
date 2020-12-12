---
title: "Python HTTP Methods Tutorial"
description: "Learn the most common HTTP Methods like GET, POST, PUT and DELETE with Requests library and Github API."
date: 2020-12-12T06:28:24+05:30
draft: true
image: /img/python-http-methods/python-http-method.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

In this article, we will focus on learning about the 4 common HTTP methods - `GET`, `POST`, `PUT` and `DELETE`. We will learn about their properties and experiment with the Github API using python's **Requests** library to get a strong understanding of how these HTTP methods are used in real life projects.

If you prefer to watch videos over reading articles, check out [this video](https://youtu.be/LdKR61y-EbA) on our Youtube channel.

**Contents of this article**

1. [What is HTTP?](#what-is-http)
2. [GET Method and GET Request Example](#get-method-and-get-request-example)
3. [POST Method and POST Request Example](#post-method-and-post-request-example)
4. [PUT Method and PUT Request Example](#put-method-and-put-request-example)
5. [DELETE Method and DELETE Request Example](#delete-method-and-delete-request-example)

#### What is HTTP?

The Hypertext Transfer Protocol (HTTP) is designed to enable communications between clients and servers by working as a response-request protocol.

**Example:** A client (browser) sends an HTTP request to the server; then the server returns a response to the client. The response will contain the status information about the request and may also contain the requested content (if it is available).

![Request - Response Protocol](/img/python-http-methods/request-response-cycle.png)

#### GET Method and GET Request Example

The HTTP GET method is used to request a resource from the server. The GET request should only receive data. It shouldn't change the state of the server. If you want to change data on the server, use POST, PUT, PATCH or DELETE methods.

HTTP GET requests don't have a message body. But you still can send data to the server using the URL parameters. However, that has a limitation of the maximum size of url, which is about 2000 characters (depends on the browser).

The HTTP GET method is defined as **idempotent**, which means that multiple identical GET requests should have the same effect as a single GET request.

One way to demonstrate a GET request would be fetching the existing repositories from your Github account. You can find the documentation for the Github API [here](https://docs.github.com/en/free-pro-team@latest/rest).

Before you start, you need to create a **Personal Access Token** in your Github settings. Once you have the token, create a `.env` file and store it.

```bash
# .env 
OAUTH_TOKEN="MY_PERSONAL_ACCESS_TOKEN"
``` 

You can use python's `dotenv` library to use your environment variable in your code. This is the best practice for using environment variables as it keeps them secure.

Let's go ahead and write our code to fetch all the repositories for our account on Github.
```python3
# Fetching Github repositories from an authenticated user
# Documentation - https://bit.ly/3qLu2sW

import requests as r
import json
import base64
from dotenv import load_dotenv
import os

load_dotenv()

oauth_token = os.getenv("OAUTH_TOKEN")

#Get all repositories from Github
base_url = "https://api.github.com/user/repos"
response = r.get(base_url,
           headers={'Authorization': 'token {}'.format(oauth_token)}
           )

for x in response.json():
    print(x["name"])
```

As you can see, we are passing our `OAUTH_TOKEN` in our headers in our GET request for authorization. This allows Github to verify our account and return the repositories that are present.

###### Important points about GET request
1. GET requests can be cached
2. GET requests remain in the browser history
3. GET requests can be bookmarked
4. GET requests should never be used when dealing with sensitive data 

#### POST Method and POST Request Example

The HTTP POST method is used to create or add a resource on to the server. Unlike GET request, the POST requests may change the server state.

You can send data to the server in the **body of the POST message**. The type and size of data are not limited. But you must specify the data type in the Content-Type header and the data size in the Content-Length header fields. The HTTP POST requests can also send data to the server using the URL parameters. In this case, you are limited to the maximum size of the URL, which is about 2000 characters (it depends on the browser).

The HTTP POST method is **not idempotent**, which means that sending an identical POST request multiple times may additionally affect the state or cause further side effects.

One way to demonstrate a POST request would be creating a new repository in your Github account.

```python3
# Creating a new repository for an authenticated user
# Documentation - https://bit.ly/3oGRqpC

import requests as r
import json
import base64
from dotenv import load_dotenv
import os

load_dotenv()

oauth_token = os.getenv("OAUTH_TOKEN")

base_url = "https://api.github.com/user/repos"
repo_config = json.dumps({"name":"Http Methods Tutorial",
                          "auto_init": True,
                          "private": False,
                          "gitignore_template": "nanoc" })

response = r.post(base_url,
                  data = repo_config,
                  headers={'Authorization': 'token {}'.format(oauth_token)}
                  )
print(response.status_code)
print(response.json())
```

In the above code, I have created a variable called `repo_config`, which stores the information about my new repository in json format**(Important)**.
`name` is a required parameter for creating a new repository on Github. Rest of the parameters like `auto_init`, `private` and `gitignore_template` are not mandatory in your POST request.

If your request runs successfully, you get a response like this.
```text
201
```

```json
{'id': 320728459, 'node_id': 'xxxxxxxxxxyyyyyyyyyyzzzzz', 'name': 'Http-Methods-Tutorial', 'full_name': 'pylenin/Http-Methods-Tutorial', 'private': False, 'owner': {'login': 'pylenin', 'id': 99999, 'node_id': 'MDQ6VXNlcjQ0NzMyNjE1', 'avatar_url': 'https://avatars3.githubusercontent.com/u/44732615?v=4', 'gravatar_id': '', 'url': 'https://api.github.com/users/pylenin', 'html_url': 'https://github.com/pylenin', 'followers_url': 'https://api.github.com/users/pylenin/followers', 'following_url': 'https://api.github.com/users/pylenin/following{/other_user}', 'gists_url': 'https://api.github.com/users/pylenin/gists{/gist_id}', 'starred_url': 'https://api.github.com/users/pylenin/starred{/owner}{/repo}', 'subscriptions_url': 'https://api.github.com/users/pylenin/subscriptions', 'organizations_url': 'https://api.github.com/users/pylenin/orgs', 'repos_url': 'https://api.github.com/users/pylenin/repos', 'events_url': 'https://api.github.com/users/pylenin/events{/privacy}', 'received_events_url': 'https://api.github.com/users/pylenin/received_events', 'type': 'User', 'site_admin': False}, 'html_url': 'https://github.com/pylenin/Http-Methods-Tutorial', 'description': None, 'fork': False, 'url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial', 'forks_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/forks', 'keys_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/keys{/key_id}', 'collaborators_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/collaborators{/collaborator}', 'teams_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/teams', 'hooks_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/hooks', 'issue_events_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/issues/events{/number}', 'events_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/events', 'assignees_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/assignees{/user}', 'branches_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/branches{/branch}', 'tags_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/tags', 'blobs_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/git/blobs{/sha}', 'git_tags_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/git/tags{/sha}', 'git_refs_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/git/refs{/sha}', 'trees_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/git/trees{/sha}', 'statuses_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/statuses/{sha}', 'languages_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/languages', 'stargazers_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/stargazers', 'contributors_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/contributors', 'subscribers_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/subscribers', 'subscription_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/subscription', 'commits_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/commits{/sha}', 'git_commits_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/git/commits{/sha}', 'comments_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/comments{/number}', 'issue_comment_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/issues/comments{/number}', 'contents_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/contents/{+path}', 'compare_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/compare/{base}...{head}', 'merges_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/merges', 'archive_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/{archive_format}{/ref}', 'downloads_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/downloads', 'issues_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/issues{/number}', 'pulls_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/pulls{/number}', 'milestones_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/milestones{/number}', 'notifications_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/notifications{?since,all,participating}', 'labels_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/labels{/name}', 'releases_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/releases{/id}', 'deployments_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/deployments', 'created_at': '2020-12-12T02:11:36Z', 'updated_at': '2020-12-12T02:11:37Z', 'pushed_at': '2020-12-12T02:11:39Z', 'git_url': 'git://github.com/pylenin/Http-Methods-Tutorial.git', 'ssh_url': 'git@github.com:pylenin/Http-Methods-Tutorial.git', 'clone_url': 'https://github.com/pylenin/Http-Methods-Tutorial.git', 'svn_url': 'https://github.com/pylenin/Http-Methods-Tutorial', 'homepage': None, 'size': 0, 'stargazers_count': 0, 'watchers_count': 0, 'language': None, 'has_issues': True, 'has_projects': True, 'has_downloads': True, 'has_wiki': True, 'has_pages': False, 'forks_count': 0, 'mirror_url': None, 'archived': False, 'disabled': False, 'open_issues_count': 0, 'license': None, 'forks': 0, 'open_issues': 0, 'watchers': 0, 'default_branch': 'main', 'permissions': {'admin': True, 'push': True, 'pull': True}, 'allow_squash_merge': True, 'allow_merge_commit': True, 'allow_rebase_merge': True, 'delete_branch_on_merge': False, 'network_count': 0, 'subscribers_count': 1}
```

###### Important points about POST request

1. POST requests are never cached
2. POST requests do not remain in the browser history
3. POST requests cannot be bookmarked

#### PUT Method and PUT Request Example

While the POST method creates or adds a resource on the server,the HTTP PUT method is used to update an existing resource on the server. Unlike GET request, the HTTP PUT request may change the server state.

You can send data to the server in the body of the HTTP PUT request. The type and size of data are not limited. But you must specify the data type in the Content-Type header and the data size in the Content-Length header fields. You can also post data to the server using URL parameters with a PUT request. In this case, you are limited to the maximum size of the URL, which is about 2000 characters (depends on the browser).

The HTTP PUT method is defined as **idempotent**, which means that multiple identical HTTP PUT requests should have the same effect as a single request.

Best way to demonstrate a PUT request would be to create a new file in your repository and then update the file.

We will first create a new file called `hello.txt` in our repository. According to Github API documentation, we have to pass in a commit message and the content of the file in **base 64 encoding**.

```python3
# Creating a new file in your repository
# Documentation - https://bit.ly/37bcjna

import requests as r
import json
import base64
from dotenv import load_dotenv
import os

load_dotenv()

oauth_token = os.getenv("OAUTH_TOKEN")

# Create a new file
base_url = "https://api.github.com/repos/pylenin/Http-Methods-Tutorial/contents/hello.txt"
base64_string = base64.b64encode(bytes("Hi there", 'utf-8'))
data = {"message":"Creating a new file",
        "content":base64_string.decode('utf-8')
        }

response = r.put(base_url,
           data = json.dumps(data),
           headers={'Authorization': 'token {}'.format(oauth_token)})

print(response.status_code)
print(response.json())
```

If the above code runs successfully, you should see your response like this.

```text
201
```

```json
{'content': {'name': 'hello.txt', 'path': 'hello.txt', 'sha': 'xxxYYYYZZZZ', 'size': 8, 'url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/contents/hello.txt?ref=main', 'html_url': 'https://github.com/pylenin/Http-Methods-Tutorial/blob/main/hello.txt', 'git_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/git/blobs/3888570c7badfe7312fd22f34dec066f21671efd', 'download_url': 'https://raw.githubusercontent.com/pylenin/Http-Methods-Tutorial/main/hello.txt', 'type': 'file', '_links': {'self': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/contents/hello.txt?ref=main', 'git': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/git/blobs/3888570c7badfe7312fd22f34dec066f21671efd', 'html': 'https://github.com/pylenin/Http-Methods-Tutorial/blob/main/hello.txt'}}, 'commit': {'sha': '0e66147d04858bf8049c6d47dada4d190e7a1484', 'node_id': 'MDY6Q29tbWl0MzIwNzI4NDU5OjBlNjYxNDdkMDQ4NThiZjgwNDljNmQ0N2RhZGE0ZDE5MGU3YTE0ODQ=', 'url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/git/commits/0e66147d04858bf8049c6d47dada4d190e7a1484', 'html_url': 'https://github.com/pylenin/Http-Methods-Tutorial/commit/0e66147d04858bf8049c6d47dada4d190e7a1484', 'author': {'name': 'pylenin', 'email': '44732615+pylenin@users.noreply.github.com', 'date': '2020-12-12T02:46:11Z'}, 'committer': {'name': 'pylenin', 'email': '44732615+pylenin@users.noreply.github.com', 'date': '2020-12-12T02:46:11Z'}, 'tree': {'sha': '99a54733a0e3afc986a383c4f06a8b301a536e3e', 'url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/git/trees/99a54733a0e3afc986a383c4f06a8b301a536e3e'}, 'message': 'Creating a new file', 'parents': [{'sha': '7cf37293d9f0972131986232004dca47eef9f700', 'url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/git/commits/7cf37293d9f0972131986232004dca47eef9f700', 'html_url': 'https://github.com/pylenin/Http-Methods-Tutorial/commit/7cf37293d9f0972131986232004dca47eef9f700'}], 'verification': {'verified': False, 'reason': 'unsigned', 'signature': None, 'payload': None}}}
```

Notice how we receive a **hash value(sha)** in our response. That is the hash value of our commit. Further operations should always reference the hash value(sha) of their previous commits.

Once your `hello.txt` file is successfully created, let's update the file. Currently, `Hi there` is the content in that file. For demonstration purpose, let's change it `Hi there ! Second time`.

```python3
# Updating the contents of a file in your repository
# Documentation - https://bit.ly/37bcjna

import requests as r
import json
import base64
from dotenv import load_dotenv
import os

load_dotenv()

oauth_token = os.getenv("OAUTH_TOKEN")

# Updating the newly created file
base_url = "https://api.github.com/repos/pylenin/Http-Methods-Tutorial/contents/hello.txt"
base64_string = base64.b64encode(bytes("Hi there ! Second time", 'utf-8'))
data = {"message":"Creating a new file",
        "content":base64_string.decode('utf-8'),
        "sha":"xxxYYYYZZZZ"
        }

response = r.put(base_url,
           data = json.dumps(data),
           headers={'Authorization': 'token {}'.format(oauth_token)})
print(response.status_code)
print(response.json())
```

As you can see, we are also passing the `hash key(sha)` parameter in our json body this time. It references to the hash key(sha) value returned from our response from creating the `hello.txt` file.

If the above code runs successfully, you should see the response like this.

```text
200
```

```json
{'content': {'name': 'hello.txt', 'path': 'hello.txt', 'sha': 'abababccdd', 'size': 22, 'url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/contents/hello.txt?ref=main', 'html_url': 'https://github.com/pylenin/Http-Methods-Tutorial/blob/main/hello.txt', 'git_url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/git/blobs/0bb173c7d1e417f218d25f963c537e67a608b7a5', 'download_url': 'https://raw.githubusercontent.com/pylenin/Http-Methods-Tutorial/main/hello.txt', 'type': 'file', '_links': {'self': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/contents/hello.txt?ref=main', 'git': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/git/blobs/0bb173c7d1e417f218d25f963c537e67a608b7a5', 'html': 'https://github.com/pylenin/Http-Methods-Tutorial/blob/main/hello.txt'}}, 'commit': {'sha': '87896c52ae208caeb985861e0d693670fc4f3538', 'node_id': 'MDY6Q29tbWl0MzIwNzI4NDU5Ojg3ODk2YzUyYWUyMDhjYWViOTg1ODYxZTBkNjkzNjcwZmM0ZjM1Mzg=', 'url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/git/commits/87896c52ae208caeb985861e0d693670fc4f3538', 'html_url': 'https://github.com/pylenin/Http-Methods-Tutorial/commit/87896c52ae208caeb985861e0d693670fc4f3538', 'author': {'name': 'pylenin', 'email': '44732615+pylenin@users.noreply.github.com', 'date': '2020-12-12T02:52:57Z'}, 'committer': {'name': 'pylenin', 'email': '44732615+pylenin@users.noreply.github.com', 'date': '2020-12-12T02:52:57Z'}, 'tree': {'sha': 'de61ccab752461577ccc01fefcd85fdcfb717fc4', 'url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/git/trees/de61ccab752461577ccc01fefcd85fdcfb717fc4'}, 'message': 'Creating a new file', 'parents': [{'sha': '0e66147d04858bf8049c6d47dada4d190e7a1484', 'url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial/git/commits/0e66147d04858bf8049c6d47dada4d190e7a1484', 'html_url': 'https://github.com/pylenin/Http-Methods-Tutorial/commit/0e66147d04858bf8049c6d47dada4d190e7a1484'}], 'verification': {'verified': False, 'reason': 'unsigned', 'signature': None, 'payload': None}}}
```

###### Important points about PUT request

1. PUT requests are never cached
2. PUT requests do not remain in the browser history
3. PUT requests cannot be bookmarked

#### DELETE Method and DELETE Request Example

The HTTP DELETE method is used to delete a resource from a server. Unlike GET requests, the DELETE requests may change the state of a server.

If you send a message body on a DELETE request, it might cause some servers to reject the request.
But you still have the option of sending data to the server using URL parameters.

The DELETE method is defined as **idempotent**, which means that multiple identical DELETE requests should have the same effect as a single request.

In order to demonstrate this method, let's try to delete the `hello.txt` file. Based on the documentation, we have to mention a commit message and the `hash key(sha)` of the previous commit.

```python3
# Delete "hello.txt" file
# Documentation - https://bit.ly/3mi10xO

import requests as r
import json
import base64
from dotenv import load_dotenv
import os

load_dotenv()

oauth_token = os.getenv("OAUTH_TOKEN")

# Delete the file
base_url = "https://api.github.com/repos/pylenin/Http-Methods-Tutorial/contents/hello.txt"
data = {"message":"delete the file hello.txt",
        "sha":"abababccdd"}
response = r.delete(base_url,
           data = json.dumps(data),
           headers={'Authorization': 'token {}'.format(oauth_token)})
print(response.status_code)
print(response.json())
```

If the above code runs successfully, you should see your response like this.

```text
200
```

```json
{'content': None, 'commit': {'sha': 'abcxabcyabcz', 'node_id': 'MDY6Q29tbWl0MzIwNzI4NDU5OjRhZDA3NjA5ZTA4MGM0YmJlY2VjZDU0NTc0ZDY1MzkyYzg4ZDUzOTU=', 'url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial-2/git/commits/4ad07609e080c4bbececd54574d65392c88d5395', 'html_url': 'https://github.com/pylenin/Http-Methods-Tutorial-2/commit/4ad07609e080c4bbececd54574d65392c88d5395', 'author': {'name': 'pylenin', 'email': '44732615+pylenin@users.noreply.github.com', 'date': '2020-12-12T03:35:03Z'}, 'committer': {'name': 'pylenin', 'email': '44732615+pylenin@users.noreply.github.com', 'date': '2020-12-12T03:35:03Z'}, 'tree': {'sha': '44584145e6056b8662050e6345ce74ae8f1bd810', 'url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial-2/git/trees/44584145e6056b8662050e6345ce74ae8f1bd810'}, 'message': 'delete the file hello.txt', 'parents': [{'sha': '87896c52ae208caeb985861e0d693670fc4f3538', 'url': 'https://api.github.com/repos/pylenin/Http-Methods-Tutorial-2/git/commits/87896c52ae208caeb985861e0d693670fc4f3538', 'html_url': 'https://github.com/pylenin/Http-Methods-Tutorial-2/commit/87896c52ae208caeb985861e0d693670fc4f3538'}], 'verification': {'verified': False, 'reason': 'unsigned', 'signature': None, 'payload': None}}}
```

