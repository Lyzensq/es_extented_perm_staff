### Lzq#6565

Salut à tous , je vais vous apprendre à ajouter des perms à vos staffs en "Legacy" .

⭐️⭐️⭐️

Pour commencer tous se passe coter Server !

#### ####################################################################################################

➡️ Main.lua

Dans le main nous allons retouver les differents types de Groups

Ligne 259 💹 Nous avons le débuts des Groupes :

   -- Group DEV 

            if result[1].group then
                if result[1].group == "superadmin" then  -- Ne pas toucher 
                    userData.group = "_dev" --------------------------------------- Le Groupe 
                else
                    userData.group = result[1].group -- Ne pas toucher
                end
            else
                userData.group = 'user' -- Ne pas toucher
            end

💹 Pour crée un Second Groupes , il vous suffit de copier coller , comme  ceci 

  -- Group DEV 

            if result[1].group then
                if result[1].group == "superadmin" then  -- Ne pas toucher 
                    userData.group = "_dev" --------------------------------------- Le Groupe 
                else
                    userData.group = result[1].group -- Ne pas toucher
                end
            else
                userData.group = 'user' -- Ne pas toucher
            end

-- Group VOTRE CHOIX

            if result[1].group then
                if result[1].group == "superadmin" then  -- Ne pas toucher 
                    userData.group = "Votre nouveau groupe" --### ⚠️ Attention ne pas faire ca "responsable staff" (ne pas mettre un espace entre) mettre un "_" entre !
                else
                    userData.group = result[1].group -- Ne pas toucher
                end
            else
                userData.group = 'user' -- Ne pas toucher
            end

			Et enssuite la meme chose , pour en crée un autre , copié coller en dessous ....


⭐️⭐️⭐️

Faire les perms par Grades

Pour commencer tous se passe coter Server !

#### ####################################################################################################

➡️ Commands.lua

Voici une simple commande !

ESX.RegisterCommand('setjob', '_dev', function(xPlayer, args, showError) ---⚠️ On appercoit "_dev" , ceci est le groupe que g predefini au dessus , seulement ce groupe aura acces a cette commande !
	if ESX.DoesJobExist(args.job, args.grade) then
		args.playerId.setJob(args.job, args.grade)
	else
		showError(_U('command_setjob_invalid'))
	end
end, true, {help = _U('command_setjob'), validate = true, arguments = {
	{name = 'playerId', help = _U('commandgeneric_playerid'), type = 'player'},
	{name = 'job', help = _U('command_setjob_job'), type = 'string'},
	{name = 'grade', help = _U('command_setjob_grade'), type = 'number'}
}})

⚠️ Afin de d avoir un second est accès , il suffit de copier coller 

ESX.RegisterCommand('setjob', 'VOTREGROUPE', function(xPlayer, args, showError) ---⚠️ Ainsi dessuite pour le mettre in Nouveau Groupe !
	if ESX.DoesJobExist(args.job, args.grade) then
		args.playerId.setJob(args.job, args.grade)
	else
		showError(_U('command_setjob_invalid'))
	end
end, true, {help = _U('command_setjob'), validate = true, arguments = {
	{name = 'playerId', help = _U('commandgeneric_playerid'), type = 'player'},
	{name = 'job', help = _U('command_setjob_job'), type = 'string'},
	{name = 'grade', help = _U('command_setjob_grade'), type = 'number'}
}})

Vous avez L exemple de toutes facon  , dans Server ➡️ Commands.lua 

### Pas bien compliqué 🙃

📢 Si jamais vous avez un Soucis Veuillez me Mp Lzq#6565