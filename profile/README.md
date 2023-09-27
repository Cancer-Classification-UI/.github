# Cancer Classification UI Github
[![Python][Python-badge]][Python-url]
[![Go][Go-badge]][Go-url]


This is the organization github page for a Cancer Classification UI. This contains all the our current codebases for our Frontend and Backend.

Dive into any of our current repos!

# Current Architecture (WIP)
```mermaid
flowchart TB

    style AWS fill:#9f8660,rx:10,ry:10
    style Kubernetes fill:#7083a9,rx:10,ry:10
    style Frontend rx:10,ry:10
    style Backend rx:10,ry:10
    style pod1 fill:#818898,rx:10,ry:10
    style pod2 fill:#818898,rx:10,ry:10
    style pod3 fill:#818898,rx:10,ry:10
    style pod4 fill:#818898,rx:10,ry:10
    style pod5 fill:#818898,rx:10,ry:10

    %% Frontend
    WebAPI([<a href='https://github.com/Cancer-Classification-UI/Web-API-Service'>Web API</a>])

    %% APIs / Backend
    DatabaseLoginAPI[(Login API\nDatabase)]
    DatabaseCDNAPI[(CDN API\nDatabase)]
    DatabaseCoreAPI[(Core API\nDatabase)]
    DatabaseNotificationAPI[(Notification API\nDatabase)]


    %% Login API
    LoginAPI([<a href='https://github.com/Cancer-Classification-UI/Login-API-Service'>Login API</a>]) 

    DatabaseLoginAPI <--> LoginAPI
    LoginAPI <--> WebAPI


    %% CDN API
    CDNAPI([<a href='https://github.com/Cancer-Classification-UI/CDN-API-Service'>CDN API</a>]) 

    DatabaseCDNAPI <--> CDNAPI
    CDNAPI <--> WebAPI

    %% Core API
    CoreAPI([<a href='https://github.com/Cancer-Classification-UI/Core-API-Service'>Core API</a>])

    DatabaseCoreAPI <--> CoreAPI
    CoreAPI <--> WebAPI

    %% Notification API
    NotificationAPI([<a href='https://github.com/Cancer-Classification-UI/Notification-API-Service'>Notification API</a>]) 

    DatabaseNotificationAPI <--> NotificationAPI
    NotificationAPI <--> WebAPI

    subgraph AWS[fa:fa-cloud AWS]
        subgraph Kubernetes[fa:fa-dharmachakra Kubernetes Cluster]
            %% What is currently backend
            subgraph Backend[fa:fa-server Backend]
                direction TB
                subgraph pod1[fa:fa-box Pod]
                    LoginAPI
                    DatabaseLoginAPI
                end
                subgraph pod2[fa:fa-box Pod]
                    CDNAPI
                    DatabaseCDNAPI
                end
                subgraph pod3[fa:fa-box Pod]
                    CoreAPI
                    DatabaseCoreAPI
                end
                subgraph pod4[fa:fa-box Pod]
                    NotificationAPI
                    DatabaseNotificationAPI
                end
            end

            %% What is currently frontend
            subgraph Frontend[fa:fa-desktop Frontend]
                subgraph pod5[fa:fa-box Pod]
                    WebAPI
                end
            end
        end
    end

```

<!-- MARKDOWN LINKS & IMAGES -->
[Go-badge]: https://img.shields.io/badge/Go-00ADD8.svg?style=for-the-badge&logo=go&logoColor=white
[Go-url]: https://go.dev/
[Python-badge]: https://img.shields.io/badge/Python-3776AB.svg?style=for-the-badge&logo=python&logoColor=FFD343
[Python-url]: https://www.python.org/
