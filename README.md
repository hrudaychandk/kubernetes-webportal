# kubernetes-webportal

Requirements:
Create a kubernetes-webportal with
1 Database System(Persistent)
2 Web Portals(Stateless)

The Web Portals should be available at,
example.com/users
example.com/admin
example.com should also point to example.com/users
Rest all the redirects should be towards the default page of ingress.

The Database System should not be exposed to the internet, and will be used by the web portals. The credentials for the database should be injected in the web portal using secrets.
(The secrets (password for db and hostname) should be passed as files to /var/secrets)
, the files should be named hostname.txt and password.txt respectively. The database should have persistent volume attached to it.

The nodes should be tainted based on,
Frontend Nodes - 2 Web portals
Backend Nodes - 1 Database
The default backend page for the ingress, should be modified to have the following data: "Custom Default Backend"

