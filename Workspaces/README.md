# Workspaces

## Introduction


<p> It is fundamentally important that every VTEX.IO developer understands
the features and limitations of development and production workspaces,
since it is part of every development cycle. </p>

<p> Throughout your development journey you will bump into the terms
development workspace, production workspace, draft workspace and
master workspace.</p>

    $ vtex whoami

<p> Let's break down these terms into further detail.</p>

<p> <b>Master workspace: </b> The content here reflects what is served to the store's
end user. It should only be altered when you are positively certain that
your code is production ready.</p>
    
    $ vtex use {workspaceName} -p

<p> <b> Draft workspace: </b> This is where the majority of your coding takes place. It
is created by typing vtex use {workspacename}. No numbers or spaces are
allowed. Every new draft workspace is created as a copy of the master
workspace. </p>

    $ vtex use {workspaceName}

<hr>

## Safe evolution

<p> You will be coding your app initially on a draft workspace. This means that
by default it will be not receiving any traffic, because it will be of type
development. Your draft workspace can also be of type production if you
set it so .</p> 

   
<p>
Development workspace environment: Can link, develop, install and
publish apps, has more configuration freedom, but it cannot handle
production level traffic, cannot be promoted to master nor used for A/B
testing.
</p>

<p>
Production workspace environment: Can handle production level traffic,
can be used for A/B testing and can be promoted to master workspace. It
can also install apps, but cannot link them for development.
</p>

    $ vtex use master
    $ vtex use {workspacename} -p

## Isolated development environment

When using VTEX IO, every interaction with an account happens in a **workspace**, an isolated version of your store. There is a **master** workspace, which serves public traffic on the store by default. Whenever a new workspace is created, it is based on the master workspace. <br><br>
Any changes in the master workspace are automatically reflected in all other workspaces. By default, when you log in to a store you are in the `master` workspace.
You can take a look at the installed apps in this workspace by using the command `vtex list` (or the shorthand `vtex ls`).

    $ vtex ls




