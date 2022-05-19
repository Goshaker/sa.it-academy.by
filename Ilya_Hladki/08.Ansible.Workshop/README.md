## 08.Ansible_Workshop
### Log run playbook
```bash
ansible-playbook -i inventory.yaml redmine.yaml

PLAY [redmine] *********************************************************************************************************

TASK [Gathering Facts] *************************************************************************************************
Wednesday 18 May 2022  17:52:25 +0000 (0:00:00.017)       0:00:00.017 *********
ok: [redmine_8]

TASK [debug] ***********************************************************************************************************
Wednesday 18 May 2022  17:52:29 +0000 (0:00:03.581)       0:00:03.599 *********
ok: [redmine_8] => {
    "msg": "192.168.201.8"
}

TASK [mysql : MySQL. Install packages] *********************************************************************************
Wednesday 18 May 2022  17:52:29 +0000 (0:00:00.051)       0:00:03.651 *********
ok: [redmine_8]

TASK [mysql : mysql_db] ************************************************************************************************
Wednesday 18 May 2022  17:52:33 +0000 (0:00:04.396)       0:00:08.048 *********
ok: [redmine_8]

TASK [mysql : mysql_user] **********************************************************************************************
Wednesday 18 May 2022  17:52:35 +0000 (0:00:02.163)       0:00:10.211 *********
ok: [redmine_8]

TASK [app : Redmine. Install packages] *********************************************************************************
Wednesday 18 May 2022  17:52:39 +0000 (0:00:03.488)       0:00:13.699 *********
ok: [redmine_8]

TASK [app : Redmine. Clone repository] *********************************************************************************
Wednesday 18 May 2022  17:52:43 +0000 (0:00:03.895)       0:00:17.595 *********
ok: [redmine_8]

TASK [app : Redmine. Change permissions] *******************************************************************************
Wednesday 18 May 2022  17:52:44 +0000 (0:00:01.316)       0:00:18.912 *********
ok: [redmine_8]

TASK [app : Redmine. Change permissions] *******************************************************************************
Wednesday 18 May 2022  17:52:46 +0000 (0:00:01.686)       0:00:20.598 *********
ok: [redmine_8]

TASK [app : Config database] *******************************************************************************************
Wednesday 18 May 2022  17:52:47 +0000 (0:00:01.316)       0:00:21.914 *********
ok: [redmine_8]

TASK [app : Redmine. Setup 01] *****************************************************************************************
Wednesday 18 May 2022  17:52:49 +0000 (0:00:02.146)       0:00:24.061 *********
changed: [redmine_8]

TASK [app : Session store secret generation] ***************************************************************************
Wednesday 18 May 2022  17:52:55 +0000 (0:00:05.583)       0:00:29.645 *********
ok: [redmine_8]

TASK [app : Redmine. Setup 02] *****************************************************************************************
Wednesday 18 May 2022  17:52:56 +0000 (0:00:01.586)       0:00:31.231 *********
changed: [redmine_8]

TASK [app : Configuration files for virtualhost] ***********************************************************************
Wednesday 18 May 2022  17:53:08 +0000 (0:00:11.543)       0:00:42.775 *********
ok: [redmine_8]

TASK [app : meta] ******************************************************************************************************
Wednesday 18 May 2022  17:53:12 +0000 (0:00:03.635)       0:00:46.410 *********

TASK [app : Add redmine-8.sa to host file] *****************************************************************************
Wednesday 18 May 2022  17:53:12 +0000 (0:00:00.015)       0:00:46.426 *********
changed: [redmine_8]

TASK [app : uri] *******************************************************************************************************
Wednesday 18 May 2022  17:53:13 +0000 (0:00:01.231)       0:00:47.658 *********
ok: [redmine_8]

TASK [app : lineinfile] ************************************************************************************************
Wednesday 18 May 2022  17:53:14 +0000 (0:00:01.588)       0:00:49.247 *********
changed: [redmine_8]

TASK [Add redmine-8.sa to host file] ***********************************************************************************
Wednesday 18 May 2022  17:53:16 +0000 (0:00:01.669)       0:00:50.917 *********
changed: [redmine_8]

TASK [uri] *************************************************************************************************************
Wednesday 18 May 2022  17:53:22 +0000 (0:00:05.738)       0:00:56.655 *********
ok: [redmine_8]

TASK [lineinfile] ******************************************************************************************************
Wednesday 18 May 2022  17:53:27 +0000 (0:00:05.068)       0:01:01.724 *********
changed: [redmine_8]

PLAY RECAP *************************************************************************************************************
redmine_8                  : ok=20   changed=6    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

Wednesday 18 May 2022  17:53:30 +0000 (0:00:02.708)       0:01:04.432 *********
===============================================================================
app : Redmine. Setup 02 ---------------------------------------------------------------------------------------- 11.54s
Add redmine-8.sa to host file ----------------------------------------------------------------------------------- 5.74s
app : Redmine. Setup 01 ----------------------------------------------------------------------------------------- 5.58s
uri ------------------------------------------------------------------------------------------------------------- 5.07s
mysql : MySQL. Install packages --------------------------------------------------------------------------------- 4.40s
app : Redmine. Install packages --------------------------------------------------------------------------------- 3.90s
app : Configuration files for virtualhost ----------------------------------------------------------------------- 3.64s
Gathering Facts ------------------------------------------------------------------------------------------------- 3.58s
mysql : mysql_user ---------------------------------------------------------------------------------------------- 3.49s
lineinfile ------------------------------------------------------------------------------------------------------ 2.71s
mysql : mysql_db ------------------------------------------------------------------------------------------------ 2.16s
app : Config database ------------------------------------------------------------------------------------------- 2.15s
app : Redmine. Change permissions ------------------------------------------------------------------------------- 1.69s
app : lineinfile ------------------------------------------------------------------------------------------------ 1.67s
app : uri ------------------------------------------------------------------------------------------------------- 1.59s
app : Session store secret generation --------------------------------------------------------------------------- 1.59s
app : Redmine. Change permissions ------------------------------------------------------------------------------- 1.32s
app : Redmine. Clone repository --------------------------------------------------------------------------------- 1.32s
app : Add redmine-8.sa to host file ----------------------------------------------------------------------------- 1.23s
debug ----------------------------------------------------------------------------------------------------------- 0.05s
Playbook run took 0 days, 0 hours, 1 minutes, 4 seconds
```