# Flink Basics

## Word Count Program

This Word Count program is built using Apache Flink and processes text data to count the number of words that start with the letter "N". It reads input from a file, splits the lines into individual words, filters for those starting with "N", and aggregates their counts. The result is a list of matching words along with how many times they appeared. This demonstrates Flink's ability to handle simple yet powerful data transformations in a distributed environment.

### input/output

| input file [input.txt](../files/input.txt) | output file [output.txt](../files/output.txt) |
| ------------------------------------------ | --------------------------------------------- |
| Noman                                      | Nana 2                                        |
| Joyce                                      | Nanaho 2                                      |
| Noman                                      | Nate 1                                        |
| Sayuri                                     | Nicole 7                                      |
| Frances                                    | Nipul 6                                       |
| .                                          | .                                             |
| .                                          | .                                             |

### Program flowchart

![Word Count Program Flowchart](../images/wc.png)

### Jar File

link: [Download JAR](../jar_files/wordCount_example.jar)

## command to run the jar file (program)

**WC run command:**<br/>
flink run ~/Desktop/DataSet/wordCount_example.jar --input file:///home/a/Desktop/DataSet/input.txt --output file:///home/a/Desktop/DataSet/output.txt

---

## Join Program

This Apache Flink program reads two input files: person.txt containing person IDs and names, and location.txt containing IDs and locations. It performs three types of join operations—inner join, left outer join, and full outer join—based on matching IDs. The inner join returns records with matching IDs in both files, the left outer join includes all persons and adds location data if available, and the full outer join combines all records from both files, inserting null where no match exists. This demonstrates how Flink handles relational-style joins in a distributed data processing environment.

### input

| [person.txt](../files/person.txt) | [location.txt](../files/location.txt) |
| --------------------------------- | ------------------------------------- |
| 1,John                            | 1,DC                                  |
| 2,Albert                          | 2,NY                                  |
| 3,Lui                             | 4,LA                                  |
| .                                 | .                                     |
| .                                 | .                                     |

### output

| [innerJoin.txt](../files/person.txt) | [person.txt](../files/person.txt) | [person.txt](../files/person.txt) |
| ------------------------------------ | --------------------------------- | --------------------------------- |
| 1, John, DC                          | 1, John, DC                       | 1, John, DC                       |
| 2, Albert, NY                        | 2, Albert, NY                     | 1, Mohammed, DC                   |
| 4, Smith, LA                         | 3, Lui, Null                      | 6, Null, LU                       |
| .                                    | .                                 | .                                 |
| .                                    | .                                 | .                                 |

### Program flowchart

![Inner Join program Flowchart](../images/InnerJoin.drawio.png)

### JarFile: link: [Download JAR](../jar_files/J_example.jar)

## command to run the jar file (program)

**Join run command:**<br/>
flink run ~/Desktop/DataSet/J_example.jar --input1 file:///home/a/Desktop/DataSet/person.txt --input2 file:///home/a/Desktop/DataSet/location.txt --i_output file:///home/a/Desktop/DataSet/innerJoin.txt --l_output file:///home/a/Desktop/DataSet/leftJoin.txt --r_output file:///home/a/Desktop/DataSet/rightJoin.txt

---

## Word Count Streaming Program
This streaming Word Count program uses Apache Flink to process live text data from port 9999. It filters words starting with "N" and continuously updates their counts in real-time, demonstrating Flink’s streaming and stateful processing capabilities.

## input/ Output

| input (listening on the port 9999 for stream data) | output file [wc_stream.txt](../files/streaming/wc_streaming_output.txt) |
| ------------------------------------------ | --------------------------------------------- |
| Ni                                         | (Ni,1)                                        |
| Noman                                      | (Noman,1)                                     |
| Noman                                      | (Noman,2)                                     |
| Nickle                                     | (Nickle,1)                                    |
| Nickle                                     | (Nickle,2)                                    |
| .                                          | .                                             |
| .                                          | .                                             |

## program flowchart

## Jar File

link: [Download JAR](../jar_files/WordCount_streaming.jar)

## command to run the jar file (program)

**open a TCP port to listen to:**<br/>
nc -l 9999

**WC streaming jar run command:**<br/>
flink run ~/Desktop/dataStream/WordCount_streaming.jar --output file:///home/a/Desktop/dataStream/wc_streaming_output.txt



---

## Average Profit Program 
This Apache Flink program reads sales data containing date, month, category, item, and profit. It groups the data by month and calculates the average profit per item sold for each month. This example showcases Flink’s capability to perform aggregations and transformations on structured streaming data.

### input/output

| input file [avg.txt](../files/streaming/avg.txt) | output file [avg_output.txt](../files/streaming/avg_output.txt) |
| -------------------------------------------- | ----------------------------------------------------- |
| 01-06-2018,June,Category5,Bat,12              | (June,12.0)                                           |
| 01-06-2108,June,Category4,Perfume,10          | (June,11.0)                                           |
| 13-07-2018,July,Category1,Television,50       | (July,50.0)                                           |
| ...                                          | ...                                                  |
| 26-08-2018,August,Category1,Watch,39          | (August,34.44444444444444)                           |

### Program flowchart

![Average Profit Flowchart](../images/AVG_profit.drawio.png)

### Jar File

link: [Download JAR](../jar_files/avgProfit_streaming.jar)

## command to run the jar file (program)

**Average Profit run command:**  
flink run ~/Desktop/dataStream/avgProfit_streaming.jar --input file:///home/a/Desktop/dataStream/avg.txt --output file:///home/a/Desktop/dataStream/avg_output.txt

---
