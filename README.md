# Currency Conversion
#include <stdio.h>
// Defining a structure to represent the name and exchange rate of the currency
typedef struct  {
    char name[100]; 
    float exchange_rate; 
} Currency;
//Declaring the function name convert
float convertcurrency(float amt, Currency from, Currency to);
int main() {
    Currency currencies[] = 
    {
        {"Euro: EUR", 0.011},  // 1 INR = 0.011 EUR
        {"Japanese Yen: JPY", 1.798},  // 1 INR = 1.798 JPY
        {"Chinese Yuan: CNY", 0.085},  // 1 INR = 0.085 CNY
        {"Swedish Krona: SEK", 0.115},  // 1 INR = 0.115 SEK
        {"British Pound: GBP", 0.010},  // 1 INR = 0.010 GBP
        {"Russian Rubble: RUB", 0.980},  // 1 INR = 0.980 RUB
        {"Brazilian Real: BRL", 0.075},  // 1 INR = 0.075 BRL
        {"South Korean Won: KRW", 16.057},  //1 INR = 16.057 KRW
        {"Mexican Peso: MXN", 0.271},  // 1 INR = 0.271 MXN
        {"New Zealand Dollar: NZD", 0.020},  // 1 INR = 0.020 NZD
        {"Canadian Dollar: CAD", 0.017}, //1 INR = 0.017 CAD
        {"Australian Dollar: AUD", 0.018},  // 1 INR = 0.018 AUD
        {"Swiss Franc: CHF", 0.012},  // 1 INR = 0.012 CHF
        {"Indian Rupee: INR", 1.000},  // 1 INR = 1.000INR
        {"Malaysian Ringgit: MYR", 0.056}, //1 INR=0.0560MYR
        {"Argentine Peso: ARS", 1.282},  // 1 INR = 1.282ARS
        {"Thai Baht: THB", 0.452},  // 1 INR = 0.452THB
        {"Pakistani Rupee: PKR", 2.27},  // 1 INR = 2.27 PKR
        {"Turkish Lira: TRY", 0.108},  // 1 INR = 0.108 TRY
        {"Singapore Dollar: SGD", 0.018},  // 1 INR = 1.0.018 SGD
        {"Kuwati Dollar: KWD", 0.004},  // 1 INR = 0.004 KWD
        {"Saudi Riyal: SAR", 0.050},  // 1 INR = 0.050 SAR
        {"Hong Kong Dollar: HKD", 0.104},  // 1 INR = 0.104 HKD
        {"UAE Dirham: AED", 0.049},  // 1 INR = 0.049 AED
        {"Qatari Riyal: QAR", 0.048},  // 1 INR = 0.048 QAR
        {"Omani Riyal: OMR", 0.005},  // 1 INR = 0.005 OMR
        {"Bahrani Dinar: BHD", 0.005},  // 1 INR = 0.005 BHD
        {"Sri Lankan Rupee: LKR",2.66}, // 1 INR = 2.660 LKR 
        {"Philippine Peso: PHP ", 0.68},  // 1 INR = 0.680 PHP
        {"Bangladeshi Taka: BDT", 1.180}, //1 INR = 1.180 BDT
        {"Egyptian Pound: EGP",0.220}, //1 INR = 0.220 EGP
        {"Indonesian Rupiah:IDR",198.620}, //1 INR =198.620 IDR
        {"Vietnamese Dong: VND",298.760}, //1 INR = 298.760 VND
        {"Philippine Peso: PHP",0.680}, //1 INR = 0.680 PHP
        {"Nepalese Rupee: NPR",1.640}, //1 INR = 1.640 NPR
        {"Afghan Afghani: AFN",1.140}, //1 INR = 1.140 AFN
        {"Iraqi Dinar: IQD",16.340}, //1 INR = 16.340 IQD
        {"Armenian Dram: AMD",6.780}, // 1 INR = 6.780 AMD
        {"Nigerian Naira: NGN",5.240}, // 1 INR = 5.240 NGN
        {"Colombian Peso: COP",51.830}, // 1 INR = 51.830 COP
        {"Chilean Peso: CLP ",11.430}, //1 INR = 11.430 CLP
        {"Israeli Shekel: ILS",0.046}, // 1 INR = 0.046 ILS
        {"Jordanian Dinar: JOD",0.010}, // 1 INR = 0.010 JOD
        {"Lebanese Pound: LBP",20.900}, // 1 INR = 20.900 LBP
        {"Kazakhstani Tenge: KZT ",6.010}, //1 INR = 6.010 KZT
        {"Ukrainian Hryvnia: UAH",0.308}, //1 INR = 0.380 UAH
        {"Bulgarian Lev: BGN",0.022}, // 1 INR = 0.022 BGN
        {"Czech Koruna: CZK ",0.308}, //1 INR = 0.308 CZK
        {"Icelandic Krona: ISK ",1.890}, //1 INR = 1.890 ISK
        {"Kenyan Shilling: KES ",1.551}, //1 INR = 1.551 KES
        };
    int inputchoice, outputchoice;
    float amt;
    //giving the heading of the program to be performed 
    printf("PROGRAM ON:- CURRENCY CONVERSION\n\n");
    //what is currency conversion??
    printf("Currency conversion : It refers to the process of converting one currency into another at a specific exchange rate. This is typically done for various reasons, such as international trade, travel, investment, or financial transactions. The exchange rate represents the value of one currency in terms of another currency.\n\n");
    
    //why is currency conversion needed?
    printf("Currency conversion is needed for international trade, travel, investment, remittances, financial transactions, diversification, and arbitrage. It enables individuals, businesses, and governments to interact with the global economy by converting one currency into another at specific exchange rates.\n\n");
    
    printf("Though there are many currencies, here i have done this code for 50 currencies\n\n");

    // Display available currencies
    
    printf("Available currencies:\n\n");
    for (int i = 0; i < sizeof(currencies) / sizeof(currencies[0]); i++) 
    {
        printf("%d) %s\n", i + 1, currencies[i].name);
    }

    // The user inputs the details of the currency conversion
    
    printf("\nEnter the number of the currency to convert from: ");
    scanf("%d", &inputchoice);
        if (inputchoice > 50 || inputchoice < 1)
        {
        printf("Invalid input. Please enter a number between 1 and 50.\n");
        return 1; 
       }
    printf("Enter the number of the currency to convert to: ");
    scanf("%d", &outputchoice);
     if (outputchoice > 50 || outputchoice < 1)
     {
        printf("Invalid input. Please enter a number between 1 and 50.\n");
        return 1;
     }
    printf("Enter amount: ");
    scanf("%f", &amt);

    //Function  Performing conversion
    float result = convertcurrency(amt, currencies[inputchoice - 1], currencies[outputchoice - 1]);

    // Display result
    printf("%.2f %s is %.2f %s\n", amt, currencies[inputchoice - 1].name, result, currencies[outputchoice - 1].name);

    return 0;
}

// Function to convert amount from one currency to another
float convertcurrency(float amt, Currency from, Currency to)
{
    // Convert amount from "from" currency to USD and then from USD to "to" currency
    return amt * (1 / from.exchange_rate) * to.exchange_rate;
    
}
