# javascrap

package javascraper;

import java.io.IOException;
import org.jsoup.Jsoup;

import org.jsoup.nodes.Document;
import org.jsoup.nodes.Element;
import org.jsoup.select.*;

public class HtmlParser {

public static void main(String[] args) throws IOException{
    String url = "http://fskm.uitm.edu.my/v1/fakulti/staff-directory/academic/1097.html";
    Document doc = Jsoup.connect(url).get();

    Element table = doc.getElementById("mytable");
    
    //Get text inside Element 
    Elements rows = table.getElementsByTag("TR");
    for (Element row : rows) 
    {
            Elements tds = row.getElementsByTag("TD");
            for (int i = 0; i < tds.size(); i++) 
            {
                    if (i == 1) System.out.println(tds.get(i).text());
            }
    }
}
}
