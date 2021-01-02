# Project Reunion - PIP - Test Collaterals - PIPTool
Folders:
- Data – Contains files for exercising various scenarios related to PIPTool.exe. Files:
-- LifetimeManagerClsid.h - a C header file that contains at least one instance of the default CLSID (currently 32E7CF70-038C-429a-BD49-88850F1B4A11) for Dynamic Dependence’s LifetimeManager, to be replaced with a new GUID dynamically generated by PIPTool.exe.
-- PIPAppxManifest.xml – Sample _source_ AppxManifest.xml for the PIP to be processed by PIPTool.exe to produce the actual AppxManifest.xml for use in the PIP’s main package. This input xml contains:
--- an instance of the default CLSID (currently 32E7CF70-038C-429a-BD49-88850F1B4A11) to be replaced by PIPTool.exe.
--- At least one Properties element in an Extension element to be filtered out by PIPTool.exe to generate the actual AppxManifest.xml.
- PIPToolTest – TAEF functional test that exercises various scenarios by involving PIPTool.exe. A few basic scenarios:
-- Simple launch - PIPTool.exe launches fine and shows help page.
-- Properties element removed / DDLM CLSID not replaced - PIPTool.exe always try to filter away Properties elements in PIPAppxManifest.xml, but it can be told to _not_ replace the default CLISD in the PIPAppxManifest.xml and the specified header file.
-- Properties element removed / DDLM CLSID replaced – Besides filtering away Properties elements in PIPAppxManifest.xml, PIPTool.exe also consistently replaces all instances of the default CLISD in the PIPAppxManifest.xml and the specified header file.