# Flink Basics
## Word Count Program
This Word Count program is built using Apache Flink and processes text data to count the number of words that start with the letter "N". It reads input from a file, splits the lines into individual words, filters for those starting with "N", and aggregates their counts. The result is a list of matching words along with how many times they appeared. This demonstrates Flink's ability to handle simple yet powerful data transformations in a distributed environment.
### input/output
| input file [input.txt](../files/input.txt)    | output file [output.txt](../files/output.txt)    |
| ---------------------------                   | -----------------------------------------------  |
| Noman                                         | Nana 2                                           |
| Joyce                                         | Nanaho 2                                         |
| Noman                                         | Nate 1                                           |
| Sayuri                                        | Nicole 7                                         |
| Frances                                       | Nipul 6                                          |
| .                                             | .                                                |
| .                                             | .                                                |
### Program flowchart
![Word Count Program Flowchart](../images/wc.png)
### Jar File
link: [Download JAR](../jar_files/wordCount_example.jar)



