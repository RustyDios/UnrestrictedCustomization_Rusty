You created an XCOM 2 Mod Project!

NOPE !!

I cloned one and 'fixed' it

=====================================
ADDED PART FROM THE UC COMMENTS		https://steamcommunity.com/sharedfiles/filedetails/?id=1135440846
=====================================
jeb 6 Jun @ 10:23am 
@Toxic Frog: Will this mod ever be updated to address the issues many users have mentioned?

For example making this work with Female Clothing Pack and other mods that use the same archetype name for multiple body parts is a pretty easy fix.

In uc_BodyPartLoader.uc:

if( _archetype == none ) {
_archetype = class'uc_BodyPartArchetype'.static.CreateBodyPartArchetype( _template.ArchetypeName );
_global.BodyPartArchetypesByName.Set( _template.ArchetypeName, _archetype );
} else {
_archetype.AddPartType(_partType); // fix for multiple templates
}

Then AddPartType in uc_BodyPartArchetype.uc has to be changed from private function AddPartType to public function AddPartType.
======================================
======================================
