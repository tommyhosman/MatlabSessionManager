# MatlabSessionManager, session

A MATLAB session manager which helps keep track of multiple projects.
Modified from "Editor Session Manager" at Mathworks FileExchange

## Overview

**_session_** is a class for managing the open files and layout of the MATLAB
Editor as well as the current MATLAB path.

With session, you can easily load a set of working files and path
locations. Allowing one to switch between multiple projects with a
diverse range of opened files and path locations.

It is recommended to place this file in your MATLAB directory.

The saved session data is stored in an xml file. This xml file is stored in parent folder of matlab's preferences (prefdir).
For example on a Windows OS, the xml file would be stored at "C:\Users\John\AppData\Roaming\MathWorks\MATLAB\"

This a modified version of Marshall's [Editor Session Manager](https://www.mathworks.com/matlabcentral/fileexchange/46352-editor-session-manager), a well made session manager.

Main changes include:

- Saving the current MATLAB path list (and resetting path when loading
  session)
- Saving the xml file in a single location
- Reduced call length. Now you can just type session.save( 'SaveName' )
- Code organization and comments, and other minor changes

## Commands

**session**

- save( <opt> sessionName )

  - Saves current files and path to a session called sessionName. If no
    input, a table of previous sessions is displayed and the user is
    queried for an existing or new session name.

- open( <opt> sessionName )

  - Opens the sessionName session. If no input is provided, a table of
    previous sessions is displayed and the user can choose one to open.

- delete( <opt> sessionName, <opt,default true> delConfirmation )
  - Deletes the session sessionName(s). If no input is provided, a
    table of sessions is displayed and the user is asked to choose one or several
    to delete. If delConfirmation is true (by default), then a
    confirmation message is posted before deleting.
- view( <opt> sessionName )

  - Displays information about the session sessionName. If no input is
    provided, a table of sessions is displayed and the user can choose
    one to view.

- rename( <opt> sessionName )

  - Renames session sessionName, or displays a table of sessions to
    choose to rename.

- manageSession
  - Provides an interactive command line method to call the commands
    above multiple times.

## Examples

**Save current session**

`session.save( 'thisSession' );`

**Open a new session**

`session.open( 'thisSession' );`

or

`session.open();`

which outputs

    index        name         numFiles     currentFolder            lastUsed                 lastSaved
    _____    _____________    ________    _______________    ______________________    ______________________
    1        'thisSession'    [10]        'E:\Temp\'         '24-Jan-2019 11:03:05'    '24-Jan-2019 11:01:39'
    2        'thatSession'    [11]        'E:\Temp\'         '24-Jan-2019 16:37:02'    '24-Jan-2019 16:37:02'

    Please enter option index or name (hit enter without entering anything to cancel):
