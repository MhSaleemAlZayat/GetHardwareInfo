# Get Hardware Info
This repository is a .NET Windows Forms application is a system information utility designed to retrieve and display hardware and system details using Windows Management Instrumentation (WMI). Here's a detailed breakdown:
### Source code designed by *Alireza shirazi*
![Application Image](https://github.com/MhSaleemAlZayat/GetHardwareInfo/blob/main/Get%20Hardware%20Information%20Application%20Image.png?raw=true)


### Key Features:

1. **Tabbed Interface**:
    
    - Organized into multiple tabs:
        
        - **Hardware Info**: Displays CPU, motherboard, BIOS, and other hardware components.
            
        - **Network**: Shows network adapters, configurations, and protocols.
            
        - **System Info**: Includes processes, services, drivers, and OS details.
            
        - **Data Storage**: Lists disk drives, partitions, and logical disks.
            
        - **Memory**: Provides RAM, cache, and memory device information.
            
        - **User Account & Security**: Covers user accounts, security descriptors, and event logs.
            
        - **Developer**: Focuses on COM classes, ODBC drivers, and performance counters.
            
        - **Utility**: Miscellaneous WMI classes for advanced diagnostics.
            
        - **About**: Credits the author (Alireza Shirazi) with a link to their website.
            
2. **WMI Integration**:
    
    - Uses `ManagementObjectSearcher` to query WMI classes (e.g., `Win32_Processor`, `Win32_DiskDrive`).
        
    - Dynamically populates data based on the selected WMI class in each tab's `ComboBox`.
        
3. **Filtering**:
    
    - Checkboxes labeled **"Don't Display null Value items"** to hide properties with empty values.
        
    - Implemented via the `RemoveNullValue` method, which cleans up `ListView` entries.
        
4. **Data Presentation**:
    
    - Results are shown in a `ListView` with two columns: **Name** (property) and **Value**.
        
    - Handles array types (e.g., `string[]`, `ushort[]`) by concatenating values into a single string.
        
    - Alternating row colors (white/white smoke) for readability.
        
5. **Error Handling**:
    
    - Catches exceptions during WMI queries and displays user-friendly error messages.
        

### UI Design:

- **Fixed Size**: The form cannot be maximized (`FormBorderStyle.FixedSingle`).
    
- **Responsive Layout**: `ListView` controls expand to fill the tab page.
    
- **Author Credit**: The **About** tab includes a hyperlink to `www.ShiraziOnline.net`.
    

### Code Structure:

- **Event-Driven**: Each `ComboBox` and `CheckBox` has event handlers (`SelectedIndexChanged`, `CheckedChanged`) to refresh data.
    
- **Modular Methods**:
    
    - `InsertInfo()`: Fetches WMI data and updates the `ListView`.
        
    - `RemoveNullValue()`: Filters out null entries.
        

### Use Case:

This tool is ideal for developers or system administrators needing quick access to detailed system diagnostics without using external utilities. It demonstrates effective use of WMI in .NET and provides a clean, categorized interface for exploring system properties.

### Limitations:

- Hard-coded WMI class lists may require updates if Microsoft changes WMI schemas.
    
- No export functionality for saving results.
    
- Limited error recovery (e.g., retry mechanism).
    

Overall, it’s a practical, lightweight utility for Windows system analysis, showcasing WMI integration and tabbed UI design in .NET.
