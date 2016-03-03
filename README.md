# punBB Extension: current url


## Problem description
When running NGXIN/HAPROXY or another reverse proxy in front of the punBB instalation, the **CSRF** functionality is breaked. 

    request -> nginx(https, 443) -> apache(http, 80) 


The punnBB construct the `current url` using `$_SERVER['HTTPS']` and `$_SERVER['SERVER_PORT']`.

## Solution

The problem could be solved by adding the **X-Forwarded-Proto** and  **X-Forwarded-PortP** header in the reverse proxy and installing this extension.

## Notes
Use it only in trused environment since anybody can add the HTTP header.
I opened and issue https://github.com/punbb/punbb/issues/123 to solve this problem.