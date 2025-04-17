Computers, like users, are security principals, in that:

They have an account with a sign-in name and password that Windows changes automatically on a periodic basis.
They authenticate with the domain.
They can belong to groups and have access to resources, and you can configure them by using Group Policy.
A computer account begins its lifecycle when you create the computer object and join it to your domain. After you join the computer account to your domain, day-to-day administrative tasks include:

Configuring computer properties.
Moving the computer between OUs.
Managing the computer itself.
Renaming, resetting, disabling, enabling, and eventually deleting the computer object.

Before you create a computer object in AD DS, you must have a place to put it. The Computers container is a built-in container in an AD DS domain. This container is the default location for the computer accounts when a computer joins the domain.

This container isn't an OU. Instead, it's an object of the Container class. Its common name is CN=Computers. 
There are subtle but important differences between a container and an OU. 
You can't create an OU within a container, so you can't subdivide the Computers container. 
You also can't link a Group Policy Object to a container. Therefore, we recommend that you create custom OUs to host computer objects, 
instead of using the Computers container.
