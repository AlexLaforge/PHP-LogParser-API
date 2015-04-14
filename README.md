# PHP-LogParser-API
PHP API for Microsoft Log Parser 2.2

**Sample**

    $parser = new \LogParser\LogParser();

    $inputFormat = $parser->setInputFormat ( 'fs' );

    $query = 'SELECT Path, Name, Size, LastWriteTime  FROM ' . __DIR__ . '\*.* ORDER BY Size DESC';

    $results = $parser->query ( $query );

    foreach ($results as $record)
    {
        print_r ( $record ) . "\n";
    }

**Set Input and Output Formats**

    $inputFormat = $parser->setInputFormat ( 'fs' );
    $inputFormat->recurse = 2; // Max subdirectory recursion level
    
    $outputFormat = $parser->setOutputFormat ( 'datagrid' );

**Input Formats**

*IIS Log File Input Formats*
- IISW3C - parses IIS log files in the W3C Extended Log File Format. 
- IIS - parses IIS log files in the Microsoft IIS Log File Format. 
- BIN - parses IIS log files in the Centralized Binary Log File Format. 
- IISODBC - returns database records from the tables logged to by IIS when configured to log in the ODBC Log Format. 
- HTTPERR - parses HTTP error log files generated by Http.sys. 
- URLSCAN - parses log files generated by the URLScan IIS filter. 

*Generic Text File Input Formats*
- CSV - parses comma-separated values text files. 
- TSV - parses tab-separated and space-separated values text files. 
- XML - parses XML text files. 
- W3C - parses text files in the W3C Extended Log File Format. 
- NCSA - parses web server log files in the NCSA Common, Combined, and Extended Log File Formats. 
- TEXTLINE - returns lines from generic text files. 
- TEXTWORD - returns words from generic text files. 

*System Information Input Formats*
- EVT - returns events from the Windows Event Log and from Event Log backup files (.evt files). 
- FS - returns information on files and directories. 
- REG - returns information on registry values. 
- ADS - returns information on Active Directory objects. 

*Special-purpose Input Formats*
- NETMON - parses network capture files created by NetMon. 
- ETW - parses Enterprise Tracing for Windows trace log files and live sessions. 
- COM - provides an interface to Custom Input Format COM Plugins. 

**Output Formats**

*Generic Text File Output Formats*
- NAT: formats output records as readable tabulated columns. 
- CSV: formats output records as comma-separated values text. 
- TSV: formats output records as tab-separated or space-separated values text. 
- XML: formats output records as XML documents. 
- W3C: formats output records in the W3C Extended Log File Format. 
- TPL: formats output records following user-defined templates. 
- IIS: formats output records in the Microsoft IIS Log File Format. 
  
*Special-purpose Output Formats*
- SQL - uploads output records to a table in a SQL database. 
- SYSLOG - sends output records to a Syslog server. 
- DATAGRID - displays output records in a graphical user interface. 
- CHART - creates image files containing charts.

**Requirements:**
- Installed Log Parser 2.2 - available from here - https://technet.microsoft.com/en-us/scriptcenter/dd919274.aspx

