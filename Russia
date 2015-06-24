//+-------------------------------------------------------------------------------+
//|      彦眵嚓钼 惕踵桦. senchakv@mail.ru        
//|      泥眄 镳钿箨?疣琊噌铗囗 镳钽疣祆桉蝾?疣琊噌铗麒觐?彦眵嚓钼 惕踵桦铎
//|      镳?镱滗屦骊??耧铐耔痤忄龛?戾驿箜囵钿眍泐 钺滂礤龛 蝠彘溴痤?
//|      埋?镳噔?玎睇 (?.
//+-------------------------------------------------------------------------------+

extern string 桎屙蜩翳赅蝾= "_1";

extern string _info="软纛痨屦";
extern bool   怅隷桧纛 = true;

extern string s__   ="锣膻蝽 镟瘥";
extern string 镟疣_1 = "EURUSD";
extern string 镟疣_2 = "GBPUSD";
extern string 镟疣_3 = "USDJPY";

extern string din = "蔫磬扈麇耜桢 镟疣戾蝠";
extern double 镳铞屙騙腩騙镟疣_1   = 1; 
extern double 镳铞屙騙腩騙镟疣_2   = 1; 
extern double 镳铞屙騙腩騙镟疣_3   = 1;  
extern string t1 ="--------------------------------------";
extern double 镳铞屙騙玎牮     = 10;
extern string t2 ="--------------------------------------";

extern string tf_ = "朽犷麒?蜞殪-麴彘?潆 赅驿铋 忄膻蝽铋 镟瘥";
extern int    以_镟疣_1 = 240;
extern int    以_镟疣_2 = 240;
extern int    以_镟疣_3 = 240;

extern string tf__= "朽犷麒?蜞殪-麴彘?桧滂赅蝾疣 褥矬朦";
extern int    _以_镟疣_1 = 240;
extern int    _以_镟疣_2 = 240;
extern int    _以_镟疣_3 = 240;  

extern string l_ = "暑翳鲨屙?玎忤耔祛耱?腩蜞 铗 褥矬朦襦 (0-恹觌)";
extern double 觐_镟疣_1 = 1.2;
extern double 觐_镟疣_2 = 1.2;
extern double 觐_镟疣_3 = 1.2;

extern string p_ = "襄痂钿 篑疱漤屙? 桧滂赅蝾疣";
extern int    镥痂钿_镟疣_1 = 6;
extern int    镥痂钿_镟疣_2 = 6;
extern int    镥痂钿_镟疣_3 = 6;

extern string s_    ="绣骅?疣犷螓";
extern bool   蝈牦開徉      = true;
extern bool   耦忪妁屙睇開疱骅= false;

extern string magics = "箜桕嚯 眍戾?";
extern int magic = 1;

extern string dop_ = "青镳弪 篑蜞眍怅?耩噻?镱耠?玎牮?";
extern bool 玎镳弪 = false;
//+------------------------------------------------------------------+ 
int kol;

//+------------------------------------------------------------------+ 
int init()
  {
    check();
    
    if (kol>0)
    {
      if (GlobalVariableGet(桎屙蜩翳赅蝾,"_balance")==0)
      GlobalVariableSet(桎屙蜩翳赅蝾,"_balance",AccountBalance());
    }
    
   return(0);
  }
//+------------------------------------------------------------------+  
void check()
{
 kol=0;
 
 int total = OrdersTotal() - 1;   
  for (int i = total; i >= 0; i--) 
  {
    if (OrderSelect(i, SELECT_BY_POS, MODE_TRADES)) 
    {
      if (OrderMagicNumber()==magic)
      kol++;         
    }
  }
}
//+------------------------------------------------------------------+
double value_profit(int magic)
{
   double ld_0 = 0;
   int l_ord_total_8 = OrdersTotal();
   if (l_ord_total_8 > 0) 
   {
      for (int l_pos_12 = l_ord_total_8 - 1; l_pos_12 >= 0; l_pos_12--) 
      {
         if (OrderSelect(l_pos_12, SELECT_BY_POS, MODE_TRADES))
         {
          if (OrderMagicNumber() == magic)
          ld_0 += OrderProfit() + OrderSwap()+OrderCommission();
         } 
      }
   }
  return(ld_0);
}
//+------------------------------------------------------------------+
void CloseAll(int magic)
{  
  int total = OrdersTotal() - 1;   
  for (int i = total; i >= 0; i--) 
  {
    if (OrderSelect(i, SELECT_BY_POS, MODE_TRADES)) 
    {
        if (OrderMagicNumber() == magic)
        {        
            if (OrderType() == OP_SELL || OrderType() == OP_BUY)
            OrderClose(OrderTicket(), OrderLots(), OrderClosePrice(), 20, Yellow); 
        }    
    }    
  } 
}
//+------------------------------------------------------------------+
double 褥矬朦(string 镟疣, int 以_桧濑赅, int 镥痂钿, int 徉, string type) 
{
     double dot1,dot2;   
     int 觐隷腩磴 =0;
     int 觐隷痱 =0;
     double sum_long =0;
     double sum_short=0;
     
     for(int j=徉?j<徉?镥痂钿; j++)
     {
      dot1=iClose(镟疣,以_桧濑赅,j);
      dot2=iOpen(镟疣,以_桧濑赅,j+2); 
      
      if(dot1>dot2)
      {
        sum_long+=MathAbs(dot1-dot2);
        觐隷腩磴++;
      } else
      if(dot1<dot2)
      {
        sum_short+=MathAbs(dot1-dot2);
        觐隷痱++;
      }
     }
      if (觐隷腩磴==0) 觐隷腩磴=1;
      if (觐隷痱==0) 觐隷痱=1;
      
      if (type=="long")
      return(sum_long/觐隷腩磴); else
      if (type=="short")
      return(sum_short/觐隷痱);
}
//+------------------------------------------------------------------+ 
double cost(string 镟疣, int digits, double _lot)
{
double kf;
if (digits<=4) kf=1; else kf=10;
double tickvalue =kf*MarketInfo(镟疣, MODE_TICKVALUE);
return(tickvalue * _lot);
}
//+------------------------------------------------------------------+ 
void 篑蜞眍怅?string 镟疣, double 腩? int 以, int 以_桧濑赅, double 觐, int 镥痂钿)
{
   double bid   =MarketInfo(镟疣,MODE_BID);
   double ask   =MarketInfo(镟疣,MODE_ASK);
   int    digits=MarketInfo(镟疣,MODE_DIGITS);
   
   double pp;
   int    dd;   
   
   if (digits < 4) 
   {
     pp = 0.01;
     dd = 100;
   } 
   else 
   {
     pp = 0.0001;
     dd = 10000;
   }
   
   double necessary_=(腩?100)*GlobalVariableGet(桎屙蜩翳赅蝾?"_balance");
   double lot;
   double minlot=MarketInfo(镟疣,MODE_MINLOT);
   double sumlot=0;
   double tmp_profit=0;
   double range;
   double _dot=ask+30*pp;
   
     while(tmp_profit<necessary_)
     {  
       tmp_profit=0;
       sumlot+=minlot;
       range=ask;
       tmp_profit+=(_dot-range)*dd*cost(镟疣,digits,sumlot);
     }
     lot=sumlot;
   
   double dot1,dot2,dot3;
   double dot4,dot5,dot6;
   int n,Ticket;
   if (蝈牦開徉?=true || 耦忪妁屙睇開疱骅?=true)
   {
     if (GlobalVariableGet(桎屙蜩翳赅蝾,镟疣+"_time_long")!=iTime(镟疣,以,0))
     {
       dot1=褥矬朦(镟疣,以_桧濑赅,镥痂钿,0,"long");
       dot2=褥矬朦(镟疣,以_桧濑赅,镥痂钿,1,"long");
       dot3=褥矬朦(镟疣,以_桧濑赅,镥痂钿,2,"long");
       if (dot2>=dot3 && dot1>dot2)
       {
         dot4=褥矬朦(镟疣,以_桧濑赅,镥痂钿,0,"short");
         dot5=褥矬朦(镟疣,以_桧濑赅,镥痂钿,1,"short");
         dot6=褥矬朦(镟疣,以_桧濑赅,镥痂钿,2,"short");
         if (dot6>=dot5 && dot5>=dot4)
         {
           GlobalVariableSet(桎屙蜩翳赅蝾,镟疣+"_time_long",iTime(镟疣,以,0));       
           if (觐>0) lot=sumlot*(((dot1-dot2)*100+1)*觐);
         
           while (IsTradeAllowed()==false) Sleep(0);
           n=3;
           Ticket=-1; 
           while (Ticket<0 && n>0)
           {
             Ticket=OrderSend(镟疣,OP_BUY,NormalizeDouble(lot,2),NormalizeDouble(ask,digits),3,0,0,"铕溴?腩磴 铗 瘥黻?:"+TimeToStr(TimeCurrent(),TIME_MINUTES),magic,0,Blue);
             n--;
           } 
         }
       }
     }
     if (GlobalVariableGet(桎屙蜩翳赅蝾,镟疣+"_time_short")!=iTime(镟疣,以,0))
     {
       dot1=褥矬朦(镟疣,以_桧濑赅,镥痂钿,0,"short");
       dot2=褥矬朦(镟疣,以_桧濑赅,镥痂钿,1,"short");
       dot3=褥矬朦(镟疣,以_桧濑赅,镥痂钿,2,"short");
       if (dot2>=dot3 && dot1>dot2)
       {
         dot4=褥矬朦(镟疣,以_桧濑赅,镥痂钿,0,"long");
         dot5=褥矬朦(镟疣,以_桧濑赅,镥痂钿,1,"long");
         dot6=褥矬朦(镟疣,以_桧濑赅,镥痂钿,2,"long");
         if (dot6>=dot5 && dot5>=dot4)
         {
           GlobalVariableSet(桎屙蜩翳赅蝾?镟疣+"_time_short",iTime(镟疣,以,0)); 
           if (觐>0) lot=sumlot*(((dot1-dot2)*100+1)*觐);
         
           while (IsTradeAllowed()==false) Sleep(0);
           n=3;
           Ticket=-1; 
           while (Ticket<0 && n>0)
           {
             Ticket=OrderSend(镟疣,OP_SELL,NormalizeDouble(lot,2),NormalizeDouble(bid,digits),3,0,0,"铕溴?痱 铗 瘥黻?:"+TimeToStr(TimeCurrent(),TIME_MINUTES),magic,0,Red);
             n--;
           }
         }
       }
     }
   }
   if (蝈牦開徉?=false || 耦忪妁屙睇開疱骅?=true)
   {
     if (GlobalVariableGet(桎屙蜩翳赅蝾,镟疣+"_time")!=iTime(镟疣,以,0))
     {
       GlobalVariableSet(桎屙蜩翳赅蝾,镟疣+"_time",iTime(镟疣,以,0));
       dot1=褥矬朦(镟疣,以_桧濑赅,镥痂钿,1,"long");
       dot2=褥矬朦(镟疣,以_桧濑赅,镥痂钿,2,"long");
       dot3=褥矬朦(镟疣,以_桧濑赅,镥痂钿,3,"long");
       if (dot2>=dot3 && dot1>dot2)
       {
         dot4=褥矬朦(镟疣,以_桧濑赅,镥痂钿,1,"short");
         dot5=褥矬朦(镟疣,以_桧濑赅,镥痂钿,2,"short");
         dot6=褥矬朦(镟疣,以_桧濑赅,镥痂钿,3,"short");
         if (dot6>=dot5 && dot5>=dot4)
         {
           if (觐>0) lot=sumlot*(((dot1-dot2)*100+1)*觐);
         
           while (IsTradeAllowed()==false) Sleep(0);
           n=3;
           Ticket=-1; 
           while (Ticket<0 && n>0)
           {
             Ticket=OrderSend(镟疣,OP_BUY,NormalizeDouble(lot,2),NormalizeDouble(ask,digits),3,0,0,"铕溴?腩磴 铗 瘥黻?:"+TimeToStr(TimeCurrent(),TIME_MINUTES),magic,0,Blue);
             n--;
           } 
         }
       } 
       dot1=褥矬朦(镟疣,以_桧濑赅,镥痂钿,1,"short");
       dot2=褥矬朦(镟疣,以_桧濑赅,镥痂钿,2,"short");
       dot3=褥矬朦(镟疣,以_桧濑赅,镥痂钿,3,"short");
       if (dot2>=dot3 && dot1>dot2)
       {
         dot4=褥矬朦(镟疣,以_桧濑赅,镥痂钿,1,"long");
         dot5=褥矬朦(镟疣,以_桧濑赅,镥痂钿,2,"long");
         dot6=褥矬朦(镟疣,以_桧濑赅,镥痂钿,3,"long");
         if (dot6>=dot5 && dot5>=dot4)
         {
           if (觐>0) lot=sumlot*(((dot1-dot2)*100+1)*觐);
         
           while (IsTradeAllowed()==false) Sleep(0);
           n=3;
           Ticket=-1; 
           while (Ticket<0 && n>0)
           {
             Ticket=OrderSend(镟疣,OP_SELL,NormalizeDouble(lot,2),NormalizeDouble(bid,digits),3,0,0,"铕溴?痱 铗 瘥黻?:"+TimeToStr(TimeCurrent(),TIME_MINUTES),magic,0,Red);
             n--;
           }
         }
       }
     }
   }
}
//+------------------------------------------------------------------+ 
int start()
  {
   check();
   
   if (怅隷桧纛==true)
   {     
     Display_Info(kol); 
     DrawStats(kol);
   }    
   
   if (kol==0)
   {
     GlobalVariableSet(桎屙蜩翳赅蝾,"_balance",AccountBalance());
     if (玎镳弪==false)
     {
     GlobalVariableSet(桎屙蜩翳赅蝾,镟疣_1+"_time_long",0);
     GlobalVariableSet(桎屙蜩翳赅蝾,镟疣_1+"_time_short",0);
     GlobalVariableSet(桎屙蜩翳赅蝾,镟疣_1+"_time",0);
     GlobalVariableSet(桎屙蜩翳赅蝾,镟疣_2+"_time_long",0);
     GlobalVariableSet(桎屙蜩翳赅蝾,镟疣_2+"_time_short",0);
     GlobalVariableSet(桎屙蜩翳赅蝾,镟疣_2+"_time",0);
     GlobalVariableSet(桎屙蜩翳赅蝾,镟疣_3+"_time_long",0);
     GlobalVariableSet(桎屙蜩翳赅蝾,镟疣_3+"_time_short",0);
     GlobalVariableSet(桎屙蜩翳赅蝾,镟疣_3+"_time",0);         
     } 
   }
  
   if (镟疣_1!="") 篑蜞眍怅(镟疣_1,镳铞屙騙腩騙镟疣_1,以_镟疣_1,_以_镟疣_1,觐_镟疣_1,镥痂钿_镟疣_1);
   if (镟疣_2!="") 篑蜞眍怅(镟疣_2,镳铞屙騙腩騙镟疣_2,以_镟疣_2,_以_镟疣_2,觐_镟疣_2,镥痂钿_镟疣_2);
   if (镟疣_3!="") 篑蜞眍怅(镟疣_3,镳铞屙騙腩騙镟疣_3,以_镟疣_3,_以_镟疣_3,觐_镟疣_3,镥痂钿_镟疣_3);
   
   if (kol>0)
   {
    double profit=(value_profit(magic)*100)/GlobalVariableGet(桎屙蜩翳赅蝾,"_balance");
    double close_=镳铞屙騙玎牮;

           if (profit>=close_)
           {
             CloseAll(magic);
             Sleep(5000);
           }   
   }
   
   return(0);
  }
  //+------------------------------------------------------------------+
void Display_Info(int k) { // 蔓忸?桧纛痨圉梃 ?筱塍 铌磬
    double profit=(value_profit(magic)*100)/AccountBalance();
    Comment(
            "                              彦疴屦:  ", AccountServer(), 
      "\n", "                              吗屐 C屦忮疣:  ", TimeToStr(TimeCurrent(), TIME_MINUTES), // |TIME_SECONDS
      "\n", "                              想鬻?  ",  "1:" + DoubleToStr(AccountLeverage(), 0),
      "\n", "                              拎豚眈:      ", DoubleToStr(AccountBalance(), 2),
      "\n", "                              佯邃耱忄:  ", DoubleToStr(AccountEquity(), 2),
      "\n", "                              砚钺钿眍:  ", DoubleToStr(AccountFreeMargin(), 2),      
      "\n", "                              橡栳?   ", DoubleToStr(AccountProfit(), 2),
      "\n", "                              橡铖噤赅|橡铘栩 % :   "+DoubleToStr(profit, 2),
      "\n", "                              暑腓麇耱忸 铕溴痤?     ", DoubleToStr(k, 2),      
      "\n");
}
//+------------------------------------------------------------------+
string _140 = "lblfin_";
void DrawStats(int k) {
   double profit=(value_profit(magic)*100)/AccountBalance();
   double ld_0 = GetProfitForDay(0);
   string _8 = _140 + "1";
   if (ObjectFind(_8) == -1) {
      ObjectCreate(_8, OBJ_LABEL, 0, 0, 0);
      ObjectSet(_8, OBJPROP_CORNER, 1);
      ObjectSet(_8, OBJPROP_XDISTANCE, 10);
      ObjectSet(_8, OBJPROP_YDISTANCE, 15);
   }
   ObjectSetText(_8, "青疣犷蝾?皴泐漤: " + DoubleToStr(ld_0, 2), 12, "Courier New", Red);
   ld_0 = GetProfitForDay(1);
   _8 = _140 + "2";
   if (ObjectFind(_8) == -1) {
      ObjectCreate(_8, OBJ_LABEL, 0, 0, 0);
      ObjectSet(_8, OBJPROP_CORNER, 1);
      ObjectSet(_8, OBJPROP_XDISTANCE, 10);
      ObjectSet(_8, OBJPROP_YDISTANCE, 30);
   }
   ObjectSetText(_8, "青疣犷蝾?怊屦? " + DoubleToStr(ld_0, 2), 12, "Courier New", Red);
   ld_0 = GetProfitForDay(2);
   _8 = _140 + "3";
   if (ObjectFind(_8) == -1) {
      ObjectCreate(_8, OBJ_LABEL, 0, 0, 0);
      ObjectSet(_8, OBJPROP_CORNER, 1);
      ObjectSet(_8, OBJPROP_XDISTANCE, 10);
      ObjectSet(_8, OBJPROP_YDISTANCE, 45);
   }
   ObjectSetText(_8, "青疣犷蝾?镱玎怊屦? " + DoubleToStr(ld_0, 2), 12, "Courier New", Red);
   _8 = _140 + "4";
   if (ObjectFind(_8) == -1) {
      ObjectCreate(_8, OBJ_LABEL, 0, 0, 0);
      ObjectSet(_8, OBJPROP_CORNER, 1);
      ObjectSet(_8, OBJPROP_XDISTANCE, 10);
      ObjectSet(_8, OBJPROP_YDISTANCE, 75);
   }
   ObjectSetText(_8, "拎豚眈: " + DoubleToStr(AccountBalance(), 2), 14, "Courier New", Red);
   _8 = _140 + "5";
   if (ObjectFind(_8) == -1) {
      ObjectCreate(_8, OBJ_LABEL, 0, 0, 0);
      ObjectSet(_8, OBJPROP_CORNER, 1);
      ObjectSet(_8, OBJPROP_XDISTANCE, 10);
      ObjectSet(_8, OBJPROP_YDISTANCE, 105);
   }
   ObjectSetText(_8, "橡铖噤赅: " + DoubleToStr(profit, 2), 14, "Courier New", Red); 
   _8 = _140 + "6";
   if (ObjectFind(_8) == -1) {
      ObjectCreate(_8, OBJ_LABEL, 0, 0, 0);
      ObjectSet(_8, OBJPROP_CORNER, 1);
      ObjectSet(_8, OBJPROP_XDISTANCE, 10);
      ObjectSet(_8, OBJPROP_YDISTANCE, 135);
   }   
   ObjectSetText(_8, "暑腓麇耱忸 铕溴痤? " + DoubleToStr(k, 2), 14, "Courier New", Red);
}

double GetProfitForDay(int ai_0) {
   double ld_ret_4 = 0;
   for (int l_pos_12 = 0; l_pos_12 < OrdersHistoryTotal(); l_pos_12++) {
      if (!(OrderSelect(l_pos_12, SELECT_BY_POS, MODE_HISTORY))) break;
         if (OrderCloseTime() >= iTime(Symbol(), PERIOD_D1, ai_0) && OrderCloseTime() < iTime(Symbol(), PERIOD_D1, ai_0) + 86400) ld_ret_4 += OrderProfit() + OrderSwap() + OrderCommission();
   }
   return (ld_ret_4);
}
//+------------------------------------------------------------------+
