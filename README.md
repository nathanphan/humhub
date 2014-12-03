Welcome to HumHub 
=================

HumHub is a flexible open source social network application written in PHP.

- <a href="http://humhub.org" target="_blank">**Homepage & Demo**</a>

- <a href="protected/docs/guide/administration/index.md">Installation & Admin Documentation</a>
- <a href="protected/docs/guide/developer/index.md">Developer Documentation</a>
- <a href="protected/docs/guide/theming/index.md">Theming Documentation</a>


- <a href="protected/docs/license.md">License: Dual license AGPL v3 / Proprietary</a>

change here
$fullPath = Yii::app()->params['repoHome'] . $folderName;
                @chdir($fullPath);
                //lock the repo before process
                if(PatchesManager::lock($folderName)) {
                    $pm->applyPatch($model);

                    $model->status = Patches::STATUS_OK;
                    if($model->save()) {
                        PatchesManager::sendPatchNotification($model);
                    }
