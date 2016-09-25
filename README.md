/*Данная функция проверяет находится ли Player A возле Player B в указанном радиусе*/

stock PlayerBesideTheOther(Float: radius, playerid, targetid)
{
    if(0 == IsPlayerStreamedIn(playerid, targetid))
        return 0;

    new Float: pos_x,
        Float: pos_y,
        Float: pos_z;

    GetPlayerPos(targetid, pos_x, pos_y, pos_z);
    return IsPlayerInRangeOfPoint(playerid, radius, pos_x, pos_y, pos_z);
}  

/*
Данная функция возвращает:

0	Если игрок не найден, либо в не зоне радиуса.
1	Если игрок найден и в зоне радиуса.
*/

/*
Использование:

PHP код:
if(0 == PlayerBesideTheOther(5.0/*Радиус*/, playerid/*Player A*/, targetid/*Player B*/))
    return SendClientMessage(playerid, -1, !"Ошибка");
*/
