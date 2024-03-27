# Work-Hours-Calculator-with-C-Programming
using System;

class MainClass {

  public static string StringChallenge(string str) {

    // code goes here 
    string [] times = str.Split('-');
    string startTime = times[0];
    string endTime = times[1];

    int startMinutes = TimeToMinutes(startTime);

    int endMinutes = TimeToMinutes(endTime);
    int difference = endMinutes - startMinutes;

    if (difference < 0)
    {
      difference += 1440;
    } 
    return difference.ToString();
    //return str;

  }
  public static int TimeToMinutes(string time){
    string[] parts = time.Split(':');
    int hour = int.Parse(parts[0]);
    int minutes = int.Parse(parts[1].Substring(0, 2));
    string ampm = parts[1].Substring(2);

    if (ampm == "pm" && hour != 12){
      hour += 12;
    }
    else if (ampm == "am" && hour == 12){
      hour = 0;
    }
    return hour*60 + minutes;
  }

  static void Main() {  

    // keep this function call here
    Console.WriteLine(StringChallenge(Console.ReadLine()));
    
  } 

}
