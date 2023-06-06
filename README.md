## Dotnet-practice

##### Main objective is to deploy a simple dotnet application on kubernetes

* #### Resources used:
1) For docker image - https://www.youtube.com/watch?v=Po9jQS7WBDQ
2) For deploying on kubernetes - https://www.youtube.com/watch?v=ZOROT9yMp44

* #### Install dotnet sdk: https://dotnet.microsoft.com/en-us/download

* #### Steps to run a dotnet application:
    - `dotnet new webapi -n webapp`
    - `cd webapp`
    - `dotnet run`
##### For creating a sidecar container to run dotnet-monitor for the dotnet app
* ##### Important links:
    - https://github.com/dotnet/dotnet-monitor/blob/main/documentation/kubernetes.md
    - https://learn.microsoft.com/en-us/shows/on-net/diagnosing-net-6-issues-from-sidecar-containers-using-dotnet-monitor

