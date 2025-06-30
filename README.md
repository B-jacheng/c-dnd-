#include<iostream>
#include<cstdlib>
#include<ctime>
#include <cmath>
#include <vector>
#include <random>
using namespace std;
int dice(int dice1, int dice0)
{
	uniform_int_distribution<> dis(1, dice0);
	vector<int> random_numbers;
	int sum = 0;
	random_device rd;
	mt19937 gen(rd());
	for (int i = 0; i < dice1; ++i) {

		int random_number = dis(gen);  // 生成一个随机数
		random_numbers.push_back(random_number);  // 将随机数存入vector
		sum += random_number;
		
	}
return sum;
}
struct npc {
	string npcname;
	string occupation;
	int strength;
	int agility;
	int physique;
	int intellect;
	int perception;
	int charm;
	int hp;
	int weizhi;

};
struct cloth {
	string clothname;
	int ac;
};
struct weapon {
	string weaponname;
	int fanwei;
	int hurt;
};
struct gather {
	npc npc0;
	cloth cloth0;
	weapon weapon0;
};
npc player = { "", "", 8, 8, 8, 8, 8, 8, 8 ,1000}; npc enemy = { "", "", 20, 20, 20, 20, 20, 20,20,1020 };
gather player0; gather enemy0;
cloth buyi,qingjia,zhongjia,kaijia,dunpai;
weapon quantou,danshoujian,gongjian,shuangshoufu,bishou,fazhang;
void inputname(){
	cout << "请输入你的姓名" << endl;
    cin >> player.npcname;
	cout << "输入成功，你的名字是：" << player.npcname << endl;	
}
void occupationcontrol(){
	while(true){
	cout << "请选择你的职业  1战士 2游荡者 3野蛮人 4法师 5牧师 6术师" << endl;
	int occupationcontrol0;
	cin >> occupationcontrol0;
	switch (occupationcontrol0){
		case 1:
			cout << "你选择的职业是战士" << endl;	
			player.occupation = "战士";
			break;
		case 2:
		    cout << "你选择的职业是游荡者" << endl;
			player.occupation = "游荡者";
		    break; 
		case 3:
			cout << "你选择的职业是野蛮人" << endl;
			player.occupation = "野蛮人";
			break;
        case 4:
			cout << "你选择的职业是法师" << endl;
			player.occupation = "法师";
			break;
		case 5:
			cout << "你选择的职业是牧师" << endl;
			player.occupation = "牧师";
			break;
		case 6:
			cout << "你选择的职业是术师" << endl;
			player.occupation = "术师";
			break;
		default:
			cout << "输入无效，请输入对应数字" << endl;
			continue;
	}
	break;
	}
}
void pluspoint() {
	cout << "请开始加点" << endl;
	int strength=8; int agility = 8; int physique = 8; int intellect = 8; int perception = 8; int charm = 8;
    int point = 30; 
	while (point>0) {
		
	jiadian0:
		cout << "您剩余的属性点为" <<point<< endl;
		cout << "请输入你的力量属性(8到17)" << endl;
		cin >> strength;
		if (strength >= 8 && strength <= 14)
		{
			player.strength = strength;
			point = point - (strength - 8);
		}
		else if (strength >= 14 && strength <= 17)
		{
			player.strength = strength;
			point = point - 6 - ((strength - 14) * 2);
		}
		else{
			cout << "请重新输入" << endl;
		    goto jiadian0;}
		if (point <= 0) {
			break;
	    }
	jiadian1:
		cout << "您剩余的属性点为" << point << endl;
		cout << "请输入你的敏捷属性(8到17)" << endl;
		cin >> agility;
		if (agility >= 8 && agility <= 14)
		{
			player.agility = agility;
			point = point - (agility - 8);
		}
		else if (agility >= 14 && agility <= 17)
		{
			player.agility = agility;
			point = point - 6 - ((agility - 14) * 2);
		}
		else {
			cout << "请重新输入" << endl;
			goto jiadian1;
		}
		if (point <= 0) {
			break;
		}
	jiadian2:
		cout << "您剩余的属性点为" << point << endl;
		cout << "请输入你的体质属性(8到17)" << endl;
		cin >> physique;
		if (physique >= 8 && physique <= 14)
		{
			player.physique = physique;
			point = point - (physique - 8);
		}
		else if (physique >= 14 && physique <= 17)
		{
			player.physique = physique;
			point = point - 6 - ((physique - 14) * 2);
		}
		else {
			cout << "请重新输入" << endl;
			goto jiadian2;
		}
		if (point <= 0) {
			break;
		}
	jiadian3:
		cout << "您剩余的属性点为" << point << endl;
		cout << "请输入你的智力属性(8到17)" << endl;
		cin >> intellect;
		if (intellect >= 8 && intellect <= 14)
		{
			player.intellect = intellect;
			point = point - (intellect - 8);
		}
		else if (intellect >= 14 && intellect <= 17)
		{
			player.intellect = intellect;
			point = point - 6 - ((intellect - 14) * 2);
		}
		else {
			cout << "请重新输入" << endl;
			goto jiadian3;
		}
		if (point <= 0) {
			break;
		}
	jiadian4:
		cout << "您剩余的属性点为" << point << endl;
		cout << "请输入你的感知属性(8到17)" << endl;
		cin >> perception;
		if (perception >= 8 && perception <= 14)
		{
			player.perception = perception;
			point = point - (perception - 8);
		}
		else if (perception >= 14 && perception <= 17)
		{
			player.perception = perception;
			point = point - 6 - ((perception - 14) * 2);
		}
		else {
			cout << "请重新输入" << endl;
			goto jiadian4;
		}
		if (point <= 0) {
			break;
		}
	jiadian5:
		cout << "您剩余的属性点为" << point << endl;
		cout << "请输入你的魅力属性(8到17)" << endl;
		cin >> charm;
		if (charm >= 8 && charm <= 14)
		{
			player.charm = charm;
			point = point - (charm - 8);
		}
		else if (charm >= 14 && charm <= 17)
		{
			player.charm = charm;
			point = point - 6 - ((charm - 14) * 2);
		}
		else {
			cout << "请重新输入" << endl;
			goto jiadian4;
		}
		if (point <= 0) {
			break;
		}
	
		
	}
}
void zhuye()
{
	cout << "**********************" << endl;
	cout << "******1 开始游戏******" << endl;
	cout << "**********************" << endl;
	cout << "******2 查看规则******" << endl;
	cout << "**********************" << endl;
	cout << "******3 退出游戏******" << endl;
	cout << "**********************" << endl;
}
void playerxingzou() {
	playerxingzou0:
	cout << "请输入你要行走的距离(-4到4)" << endl;
	int xingzou0;
	cin >> xingzou0;
	if(-4 <= xingzou0<=-1)
	{
		cout << "您后退了"<<-(xingzou0)<<"步" << endl;
	}
	else if (1 <= xingzou0 <= 4)
	{
		cout << "您前进了" << xingzou0 << "步" << endl;
	}
	else
	{
		cout << "请正确输入" << endl;
		goto playerxingzou0;
	}
	player.weizhi=player.weizhi+xingzou0;
	
}
void enemyxingzou() {
	if (abs(enemy.weizhi - player.weizhi)>5)
	{
		if(player.weizhi<enemy.weizhi)
		{enemy.weizhi = enemy.weizhi - 5;}
		else if(player.weizhi > enemy.weizhi)
		{
			enemy.weizhi = enemy.weizhi + 5;
		}
		cout << "boss向你靠近了5步" <<"你与boss的距离为"<<abs(enemy.weizhi-player.weizhi)<<"步"<< endl;
	}
	else if (abs(enemy.weizhi - player.weizhi) <=5)
	{
		enemy.weizhi = player.weizhi;
		cout << "boss追上了你" << endl;
	}
}
void Pweapongongji()
{
	if (player0.weapon0.fanwei >= abs(enemy.weizhi - player.weizhi)) {


if (player0.npc0.strength / 2+dice(1,20)>enemy0.cloth0.ac){
	if (player0.weapon0.weaponname == "单手剑") {
		enemy.hp = enemy.hp - dice(2, 4)-(player0.npc0.strength-8)/2;
		cout << "你使用了武器"<< player0.weapon0.weaponname <<"攻击敌人造成了" << dice(2, 4) + (player0.npc0.strength-8) / 2 <<"点伤害" << endl;
	}
	else if (player0.weapon0.weaponname == "匕首") {
		enemy.hp = enemy.hp - (dice(2, 4) - 1)-player0.npc0.agility/2;
		cout << "你使用了武器" << player0.weapon0.weaponname << "攻击敌人造成了" << (dice(2, 4) - 1) +( player0.npc0.agility-8) / 2 << "点伤害" << endl;
	}
	else if (player0.weapon0.weaponname == "拳头") {
		enemy.hp = enemy.hp - dice(1, 4)-player0.npc0.strength / 2;
		cout << "你使用了武器" << player0.weapon0.weaponname << "攻击敌人造成了" << dice(1, 4) + (player0.npc0.strength - 8) / 2 << "点伤害" << endl;
	}
	else if (player0.weapon0.weaponname == "双手斧") {
		enemy.hp = enemy.hp - dice(2, 5)-player0.npc0.strength / 2;
		cout << "你使用了武器" << player0.weapon0.weaponname << "攻击敌人造成了" << dice(2, 5)  +(player0.npc0.strength - 8) / 2 << "点伤害" << endl;
	}
	else if (player0.weapon0.weaponname == "法杖") {
		enemy.hp = enemy.hp - dice(1, 5) - player0.npc0.strength / 2;
		cout << "你使用了武器" << player0.weapon0.weaponname << "攻击敌人造成了" << dice(1, 5) + (player0.npc0.strength - 8) / 2 << "点伤害" << endl;
	}}
else {
	cout << "miss" << endl;
}
	} 
	else {
		cout << "与敌人距离超出武器攻击范围" << endl;
	}
	cout << "敌人剩余血量为" <<enemy.hp<< endl;
}
void Eweapongongji() {
	if (enemy0.weapon0.fanwei >= abs(enemy.weizhi - player.weizhi)) {
		if ((enemy0.npc0.strength - 8) / 2 + dice(1, 20) > player0.cloth0.ac) {
			player.hp = player.hp - dice(2, 5) - (enemy0.npc0.strength-8) / 2;
			cout << "敌人使用了" << enemy0.weapon0.weaponname << "对你造成了" << dice(2, 5) + (enemy0.npc0.strength-8) / 2 << "点伤害" << endl;
		}
		else { cout << "miss" << endl; }





	}
	else {}
	cout << "您剩余血量为" << player.hp << endl;
}
int main(){
	//装备库

	cloth buyi = { "布衣", 10 };
	cloth qingjia = { "轻甲", 11 };
	cloth zhongjia = { "中甲", 12 };
	cloth kaijia = { "铠甲", 14 };

	//武器库
	weapon danshoujian = { "单手剑", 2, 0 };
	weapon quantou = { "拳头", 1, 0 };  // 伤害动态计算
	weapon gongjian = { "弓箭", 10, 0 };
	weapon shuangshoufu = { "双手斧", 3, 0 };
	weapon bishou = { "匕首", 1, 0 };
	weapon fazhang = { "法杖", 3, 0 };
	//敌人属性
	enemy.strength = 24; enemy.agility = 20; enemy.physique = 20;
	enemy.perception = 17; enemy.perception= 17; enemy.charm= 17;
	enemy.hp = enemy.physique; enemy.npcname = "邪念";
	enemy0.weapon0 = shuangshoufu; enemy0.cloth0 = kaijia;
    while(true){
		zhuye();
	int zhuye0 = 0;
	cout << "输入对应数字" << endl;
	cin >> zhuye0;
	
	switch (zhuye0) {
	case 1:
		goto flag;
		break;
	case 2:	
		cout << "0 骰子机制" << endl;
		cout << "1d6为掷一个六面骰子  2d4为掷两个四面的骰子取和" << endl;
		cout << "1 六维属性 " << endl;
		cout << "力敏体智感魅 基础八点 可分配属性三十点 上限为17点  9到14一级一点 14到17一级两点 每两点提升一属性检定值 向下取整" << endl;
		cout << "力量影响力量类武器近战命中以及伤害 投掷武器命中以及伤害" << endl;
		cout << "敏捷影响灵巧类武器匕首弓箭等命中以及伤害" << endl;
		cout << "体质影响血量上限" << endl;
		cout << "智力影响法术命中以及伤害" << endl;
		cout << "感知影响神术命中以及伤害" << endl;
		cout << "魅力影响术式命中以及伤害" << endl;
		cout << "2 命中与伤害" << endl;
		cout << "ac 护甲等级  ac越高越不易被敌人命中" << endl;
		cout << "战斗时，进攻方先掷一个1d20骰子，取其值加上相关属性调整值。两者之和大于防守方ac值即为命中" << endl;
		cout << "攻击命中后造成伤害为武器/道具/技能伤害加上相关属性调整值" << endl;
		cout << "战斗采用回合制，一方生命归零即为战斗结束" << endl;
	    break;
		
	case 3:	
		return 0;
		break;
	default:
		cout << "请重新输入" << endl;
		break;
	}}
    flag:  
    //输入姓名
	inputname();
	//输入职业
	occupationcontrol();
	//加点
	pluspoint();
	//玩家血量
	player.hp = player.physique;
	//显示玩家属性
	cout << "创建成功 角色属性如下" << endl;
	if (player.occupation == "战士") 
	{
		player0.npc0 = player;
		player0.weapon0 = danshoujian; cout << "已装备 单手剑" << endl;
		player0.cloth0 = kaijia; cout << "已装备 铠甲" << endl;
	}
	else if (player.occupation == "游荡者")
	{
		player0.npc0 = player;
		player0.weapon0 = bishou; cout << "已装备 匕首" << endl;
		player0.cloth0 = zhongjia; cout << "已装备 中甲" << endl;
	}
	else if (player.occupation == "野蛮人")
	{
		player0.npc0 = player;
		player0.weapon0 = shuangshoufu; cout << "已装备 双手斧" << endl;
		player0.cloth0 = buyi; cout << "已装备 布衣" << endl;
	}
	else if (player.occupation == "法师")
	{
		player0.npc0 = player;
		player0.weapon0 = fazhang; cout << "已装备 法杖" << endl;
		player0.cloth0 = buyi; cout << "已装备 布衣" << endl;
	}
	else if (player.occupation == "牧师")
	{
		player0.npc0 = player;
		player0.weapon0 = quantou; cout << "已装备 圣徽" << endl;
		player0.cloth0 = zhongjia; cout << "已装备 中甲" << endl;
	}
	else if (player.occupation == "术师")
	{
		player0.npc0 = player;
		player0.weapon0 = quantou; cout << "已装备 龙鳞" << endl;
		player0.cloth0 = qingjia; cout << "已装备 轻甲" << endl;
	}
	
	cout << "姓名    " <<player.npcname<< endl;
	cout << "职业    " << player.occupation<<endl;
	cout << "力量    " << player.strength<< "敏捷    " << player.agility <<"体质    " << player.physique
		 << "智力    " << player.intellect << "感知    " << player.perception << "魅力    " << player.charm << endl;
	player.hp == player.physique;
	cout << "生命上限" << player.hp<<endl;
	cout << "装备    " << player0.cloth0.clothname << endl;
	cout << "武器    " << player0.weapon0.weaponname << endl;
	system("pause");

    while(player.hp > 0&&  enemy.hp > 0)
	{
		
		playerxingzou();
		Pweapongongji();
		enemyxingzou();
		Eweapongongji();
	}
	return 0;
}
