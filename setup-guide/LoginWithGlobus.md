
## Introduction

This document explains how to configure a CBRAIN and NeuroHub portal
to provide a login button that works with with the Globus Auth
system.

Any CBRAIN or NeuroHub portal deployed (not just the production
ones) have this capability, but the *Login With Globus* button will
not show up until the CBRAIN administrator enter the proper
configuration information.

These instructions can be followed by a developer trying to enable
the feature on their development environment, or as documentation
for how to recreate (if needed) the button on the main NeuroHub/CBRAIN
service.

## Configure a Globus App on the Globus website

Go to:

https://www.globus.org/

and login as an appropriate user or maintainer for the feature.
This automatically give you access to the Globus developer framework,
as a side effect. Getting to the developer interface is convoluted,
so instead of trying to find it with the interface, just go directly
with this URL:

https://auth.globus.org/v2/web/developers

This page allows you to create Projects, and each project can have
several 'apps'. Create a project and create an app using the buttons
of the interface:

[[/setup-guide/images/01_globus_app.png]]

The App's configuration must include a bunch of redirect URLs. See
the screenshot below for the values currently used in production
for the CBRAIN service. For a developer's private environment, only
the localhost values (which are the only ones permitted to use plain
HTTP) are needed.

[[/setup-guide/images/02_globus_app.png]]

Within the App, a secret token must also be generated. The token will
be shown only once, but the admin should copy it some place safe, it
will be needed in the next step.

### Configure the Login button in CBRAIN

This is performed using the CBRAIN Rails console. The administrator
needs to enter two values in the configuration of the Portal: the
ID of the App created above, and the secret token.

In the CBRAIN console, find the object for the Portal. Generally,
there is only one:

```ruby
CBRAIN_main_001> p = BrainPortal.first
```

Then store the two values in the meta-data store for the Portal object:

```ruby
CBRAIN_main_001> p.meta[:globus_client_id]     = "e25e39dd-xxxxxxxxxxxxxxxxxxxxxxxxxxx"
CBRAIN_main_001> p.meta[:globus_client_secret] = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
```

At this point, the interface for both the CBRAIN and NeuroHub login
pages will show a button that says "Login With Globus". Also,
the "My Account" pages will provide a way for users to link their
CBRAIN or NeuroHub accounts to their favorite Globus identity.

