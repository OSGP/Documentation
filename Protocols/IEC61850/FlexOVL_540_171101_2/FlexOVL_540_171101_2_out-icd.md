### SSLD ICD file, FlexOVL_540_171101_2_out.icd

```xml
<?xml version="1.0" encoding="utf-8"?>
<!--Generated with ABB IEC61850 Libraries 5.3.1.25 at 1-11-2017 15:05:17.-->
<SCL xmlns="http://www.iec.ch/61850/2003/SCL" xmlns:sxy="http://www.iec.ch/61850/2003/SCLcoordinates" xmlns:esld="http://www.abb.com/61850/2006/SCL_SLD" xmlns:eComm="http://www.abb.com/61850/2009/SCL_ABBCommunication" xmlns:eABB="http://www.abb.com/61850/2010/ABBTranslations" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.iec.ch/61850/2003/SCL SCL.xsd http://www.iec.ch/61850/2003/SCLcoordinates SCL_Coordinates.xsd http://www.abb.com/61850/2006/SCL_SLD SCL_SLD.xsd http://www.abb.com/61850/2009/SCL_ABBCommunication SCL_ABBCommunication.xsd http://www.abb.com/61850/2010/ABBTranslations SCL_ABBTranslations.xsd">
  <Private type="ABB SLD">
    <esld:SLD>
      <esld:Sizes elementSize="1" />
      <esld:AlarmSettings />
      <esld:MeasurementStatus />
      <esld:DefaultColors />
      <esld:NameDisplay />
      <esld:Fonts />
      <esld:MeasurementPrecision defaultDecimals="0" />
      <esld:DisplayMultipliers />
    </esld:SLD>
    <esld:BusbarColoring triggeringTimeBuffer="0" />
  </Private>
  <Header id="ID" version="2003" revision="A" nameStructure="IEDName" />
  <Communication>
    <SubNetwork name="WA1" desc="Subnetwork" type="8-MMS">
      <Private type="ABBPCMInternalObjRef">fe64bc9f-6918-4694-b3c7-b8f84dede770</Private>
      <ConnectedAP iedName="AA1TH01" apName="S1">
        <Address>
          <P type="IP" xsi:type="tP_IP">192.168.0.10</P>
          <P type="OSI-AP-Title" xsi:type="tP_OSI-AP-Title">1,3,9999,23</P>
          <P type="OSI-AE-Qualifier" xsi:type="tP_OSI-AE-Qualifier">23</P>
          <P type="OSI-PSEL" xsi:type="tP_OSI-PSEL">00000001</P>
          <P type="OSI-SSEL" xsi:type="tP_OSI-SSEL">0001</P>
          <P type="OSI-TSEL" xsi:type="tP_OSI-TSEL">0001</P>
          <P type="IP-GATEWAY" xsi:type="tP_IP-GATEWAY">0.0.0.0</P>
          <P type="IP-SUBNET" xsi:type="tP_IP-SUBNET">255.255.255.0</P>
        </Address>
      </ConnectedAP>
    </SubNetwork>
  </Communication>
  <IED name="AA1TH01" desc="Server" type="RTU560_2" manufacturer="ABB" configVersion="1.3">
    <Private type="ABB_PCMObjectTypeName">Generic IEC61850 IED</Private>
    <Private type="ABBPCMInternalObjRef">580da69c-6a72-4d9d-8a28-0978d0d82a5b</Private>
    <Services>
      <DynAssociation />
      <GetDirectory />
      <GetDataObjectDefinition />
      <DataObjectDirectory />
      <GetDataSetValue />
      <DataSetDirectory />
      <ConfDataSet max="48" maxAttributes="450" />
      <ReadWrite />
      <ConfReportControl max="48" />
      <GetCBValues />
      <ReportSettings cbName="Conf" datSet="Conf" rptID="Dyn" optFields="Dyn" bufTime="Dyn" trgOps="Dyn" intgPd="Dyn" />
      <GSESettings cbName="Conf" datSet="Conf" appID="Conf" />
      <GOOSE max="8" />
      <ConfLNs fixPrefix="true" fixLnInst="true" />
    </Services>
    <AccessPoint name="S1">
      <Server>
        <Authentication />
        <LDevice inst="LD0">
          <LN0 lnClass="LLN0" inst="" lnType="LLN0_RTU560_2_IEC61850">
            <DataSet name="StatNrmlA" desc="Status data used for event list entries.">
              <FCDA ldInst="LD0" lnClass="LPHD" lnInst="1" doName="PhyHealth" fc="ST" />
              <FCDA ldInst="LD0" prefix="SP" lnClass="GGIO" lnInst="1" doName="Ind" fc="ST" />
              <FCDA ldInst="LD0" prefix="SP" lnClass="GGIO" lnInst="9" doName="Ind" fc="ST" />
              <FCDA ldInst="LD0" prefix="SP" lnClass="GGIO" lnInst="7" doName="Ind" fc="ST" />
              <FCDA ldInst="LD0" prefix="SP" lnClass="GGIO" lnInst="2" doName="Ind" fc="ST" />
              <FCDA ldInst="LD0" prefix="SP" lnClass="GGIO" lnInst="3" doName="Ind" fc="ST" />
              <FCDA ldInst="LD0" prefix="SP" lnClass="GGIO" lnInst="5" doName="Ind" fc="ST" />
              <FCDA ldInst="LD0" prefix="SP" lnClass="GGIO" lnInst="16" doName="Ind" fc="ST" />
              <FCDA ldInst="LD0" prefix="SP" lnClass="GGIO" lnInst="15" doName="Ind" fc="ST" />
              <FCDA ldInst="LD0" prefix="SP" lnClass="GGIO" lnInst="14" doName="Ind" fc="ST" />
              <FCDA ldInst="LD0" prefix="SP" lnClass="GGIO" lnInst="13" doName="Ind" fc="ST" />
              <FCDA ldInst="LD0" prefix="SP" lnClass="GGIO" lnInst="12" doName="Ind" fc="ST" />
              <FCDA ldInst="LD0" prefix="SP" lnClass="GGIO" lnInst="11" doName="Ind" fc="ST" />
              <FCDA ldInst="LD0" prefix="SP" lnClass="GGIO" lnInst="10" doName="Ind" fc="ST" />
              <FCDA ldInst="LD0" prefix="SP" lnClass="GGIO" lnInst="4" doName="Ind" fc="ST" />
              <FCDA ldInst="LD0" prefix="SP" lnClass="GGIO" lnInst="6" doName="Ind" fc="ST" />
              <FCDA ldInst="LD0" prefix="SP" lnClass="GGIO" lnInst="8" doName="Ind" fc="ST" />
            </DataSet>
            <ReportControl name="rcb_A" rptID="A" datSet="StatNrmlA" confRev="1" bufTime="500" buffered="true">
              <TrgOps dchg="true" qchg="true" />
              <OptFields />
            </ReportControl>
            <DOI name="NamPlt">
              <DAI name="swRev">
                <Val>12.0.3.0</Val>
              </DAI>
            </DOI>
          </LN0>
          <LN lnClass="LPHD" inst="1" lnType="LPHD_RTU560_2_IEC61850">
            <DOI name="PhyNam">
              <DAI name="swRev">
                <Val>12.0.3.0</Val>
              </DAI>
            </DOI>
            <DOI name="PhyHealth" desc="IED operable">
              <DAI name="stVal">
                <Private type="RTU560_IED_Health">1000</Private>
              </DAI>
            </DOI>
          </LN>
          <LN prefix="SP" lnClass="GGIO" inst="1" lnType="ABBRTU500_2_Rev1_SPGGIO_#LIB1" />
          <LN prefix="SP" lnClass="GGIO" inst="9" lnType="ABBRTU500_2_Rev1_SPGGIO_#LIB1" />
          <LN prefix="SP" lnClass="GGIO" inst="7" lnType="ABBRTU500_2_Rev1_SPGGIO_#LIB1" />
          <LN prefix="SP" lnClass="GGIO" inst="2" lnType="ABBRTU500_2_Rev1_SPGGIO_#LIB1" />
          <LN prefix="SP" lnClass="GGIO" inst="3" lnType="ABBRTU500_2_Rev1_SPGGIO_#LIB1" />
          <LN prefix="SP" lnClass="GGIO" inst="5" lnType="ABBRTU500_2_Rev1_SPGGIO_#LIB1" />
          <LN prefix="SP" lnClass="GGIO" inst="16" lnType="ABBRTU500_2_Rev1_SPGGIO_#LIB1" />
          <LN prefix="SP" lnClass="GGIO" inst="15" lnType="ABBRTU500_2_Rev1_SPGGIO_#LIB1" />
          <LN prefix="SP" lnClass="GGIO" inst="14" lnType="ABBRTU500_2_Rev1_SPGGIO_#LIB1" />
          <LN prefix="SP" lnClass="GGIO" inst="13" lnType="ABBRTU500_2_Rev1_SPGGIO_#LIB1" />
          <LN prefix="SP" lnClass="GGIO" inst="12" lnType="ABBRTU500_2_Rev1_SPGGIO_#LIB1" />
          <LN prefix="SP" lnClass="GGIO" inst="11" lnType="ABBRTU500_2_Rev1_SPGGIO_#LIB1" />
          <LN prefix="SP" lnClass="GGIO" inst="10" lnType="ABBRTU500_2_Rev1_SPGGIO_#LIB1" />
          <LN prefix="SP" lnClass="GGIO" inst="4" lnType="ABBRTU500_2_Rev1_SPGGIO_#LIB1" />
          <LN prefix="SP" lnClass="GGIO" inst="6" lnType="ABBRTU500_2_Rev1_SPGGIO_#LIB1" />
          <LN prefix="SP" lnClass="GGIO" inst="8" lnType="ABBRTU500_2_Rev1_SPGGIO_#LIB1" />
        </LDevice>
      </Server>
    </AccessPoint>
  </IED>
  <DataTypeTemplates>
    <LNodeType id="LLN0_RTU560_2_IEC61850" lnClass="LLN0" iedType="RTU560_2">
      <DO name="Mod" type="tcROMod_RTU560_2_IEC61850" />
      <DO name="Beh" type="tcBeh_RTU560_2_IEC61850" />
      <DO name="Health" type="tcHealth_RTU560_2_IEC61850" />
      <DO name="NamPlt" type="tcLPL_LLN0_RTU560_2_IEC61850" />
      <DO name="Loc" type="tcSPS_RTU560_2_IEC61850" />
    </LNodeType>
    <LNodeType id="LPHD_RTU560_2_IEC61850" lnClass="LPHD" iedType="RTU560_2">
      <DO name="PhyNam" type="tcDPL_RTU560_2_IEC61850" />
      <DO name="PhyHealth" type="tcHealth_RTU560_2_IEC61850" />
      <DO name="Proxy" type="tcSPS_RTU560_2_IEC61850" />
    </LNodeType>
    <LNodeType id="ABBRTU500_2_Rev1_SPGGIO_#LIB1" lnClass="GGIO" iedType="RTU560_2">
      <DO name="Mod" type="ABBRTU500_2_Rev1_tcROMod" />
      <DO name="Beh" type="ABBRTU500_2_Rev1_tcBeh" />
      <DO name="Health" type="ABBRTU500_2_Rev1_tcHealth" />
      <DO name="NamPlt" type="ABBRTU500_2_Rev1_tcLPL_#LIB1" />
      <DO name="Ind" type="ABBRTU500_2_Rev1_tcSPS" />
    </LNodeType>
    <DOType id="tcROMod_RTU560_2_IEC61850" cdc="INC" iedType="RTU560_2">
      <DA name="stVal" bType="Enum" valKind="RO" type="Mod" fc="ST" dchg="true">
        <Val>on</Val>
      </DA>
      <DA name="q" bType="Quality" valKind="RO" fc="ST" qchg="true" />
      <DA name="t" bType="Timestamp" valKind="RO" fc="ST" />
      <DA name="ctlModel" bType="Enum" valKind="RO" type="ctlModel" fc="CF">
        <Val>status-only</Val>
      </DA>
      <DA name="d" bType="VisString255" fc="DC" />
    </DOType>
    <DOType id="tcBeh_RTU560_2_IEC61850" cdc="INS" iedType="RTU560_2">
      <DA name="stVal" bType="Enum" valKind="RO" type="Beh" fc="ST" dchg="true">
        <Val>on</Val>
      </DA>
      <DA name="q" bType="Quality" valKind="RO" fc="ST" qchg="true" />
      <DA name="t" bType="Timestamp" valKind="RO" fc="ST" />
      <DA name="d" bType="VisString255" fc="DC" />
    </DOType>
    <DOType id="tcHealth_RTU560_2_IEC61850" cdc="INS" iedType="RTU560_2">
      <DA name="stVal" bType="Enum" type="Health" fc="ST" dchg="true">
        <Val>Alarm</Val>
      </DA>
      <DA name="q" bType="Quality" valKind="RO" fc="ST" qchg="true" />
      <DA name="t" bType="Timestamp" valKind="RO" fc="ST" />
      <DA name="d" bType="VisString255" fc="DC" />
    </DOType>
    <DOType id="tcLPL_LLN0_RTU560_2_IEC61850" cdc="LPL" iedType="RTU560_2">
      <DA name="vendor" bType="VisString255" valKind="RO" fc="DC">
        <Val>ABB</Val>
      </DA>
      <DA name="swRev" bType="VisString255" fc="DC">
        <Val>11.4.2.0</Val>
      </DA>
      <DA name="d" bType="VisString255" valKind="RO" fc="DC">
        <Val>RTU560_Server</Val>
      </DA>
      <DA name="configRev" bType="VisString255" fc="DC">
        <Val>1</Val>
      </DA>
      <DA name="ldNs" bType="VisString255" fc="EX">
        <Val>IEC 61850-7-4:2003</Val>
      </DA>
    </DOType>
    <DOType id="tcSPS_RTU560_2_IEC61850" cdc="SPS" iedType="RTU560_2">
      <DA name="stVal" bType="BOOLEAN" fc="ST" dchg="true">
        <Val>false</Val>
      </DA>
      <DA name="q" bType="Quality" valKind="RO" fc="ST" qchg="true" />
      <DA name="t" bType="Timestamp" valKind="RO" fc="ST" />
      <DA name="d" bType="VisString255" fc="DC" />
    </DOType>
    <DOType id="tcDPL_RTU560_2_IEC61850" cdc="DPL" iedType="RTU560_2">
      <DA name="vendor" bType="VisString255" valKind="RO" fc="DC">
        <Val>ABB</Val>
      </DA>
      <DA name="swRev" bType="VisString255" fc="DC">
        <Val>11.4.2.0</Val>
      </DA>
      <DA name="serNum" bType="VisString255" fc="DC" />
      <DA name="model" bType="VisString255" valKind="RO" fc="DC">
        <Val>RTU560_Server</Val>
      </DA>
    </DOType>
    <DOType id="ABBRTU500_2_Rev1_tcROMod" cdc="INC" iedType="RTU560_2">
      <DA name="stVal" bType="Enum" valKind="RO" type="Mod" fc="ST" dchg="true">
        <Val>on</Val>
      </DA>
      <DA name="q" bType="Quality" valKind="RO" fc="ST" qchg="true" />
      <DA name="t" bType="Timestamp" valKind="RO" fc="ST" />
      <DA name="ctlModel" bType="Enum" valKind="RO" type="ctlModel" fc="CF">
        <Val>status-only</Val>
      </DA>
      <DA name="d" bType="VisString255" fc="DC" />
    </DOType>
    <DOType id="ABBRTU500_2_Rev1_tcBeh" cdc="INS" iedType="RTU560_2">
      <DA name="stVal" bType="Enum" valKind="RO" type="Beh" fc="ST" dchg="true">
        <Val>on</Val>
      </DA>
      <DA name="q" bType="Quality" valKind="RO" fc="ST" qchg="true" />
      <DA name="t" bType="Timestamp" valKind="RO" fc="ST" />
      <DA name="d" bType="VisString255" fc="DC" />
    </DOType>
    <DOType id="ABBRTU500_2_Rev1_tcHealth" cdc="INS" iedType="RTU560_2">
      <DA name="stVal" bType="Enum" type="Health" fc="ST" dchg="true">
        <Val>Alarm</Val>
      </DA>
      <DA name="q" bType="Quality" valKind="RO" fc="ST" qchg="true" />
      <DA name="t" bType="Timestamp" valKind="RO" fc="ST" />
      <DA name="d" bType="VisString255" fc="DC" />
    </DOType>
    <DOType id="ABBRTU500_2_Rev1_tcLPL_#LIB1" cdc="LPL" iedType="RTU560_2">
      <DA name="vendor" bType="VisString255" valKind="RO" fc="DC">
        <Val>ABB</Val>
      </DA>
      <DA name="swRev" bType="VisString255" fc="DC">
        <Val>12.0.3.0</Val>
      </DA>
      <DA name="d" bType="VisString255" valKind="RO" fc="DC">
        <Val>RTU560_Server</Val>
      </DA>
      <DA name="configRev" bType="VisString255" fc="DC">
        <Val>1</Val>
      </DA>
    </DOType>
    <DOType id="ABBRTU500_2_Rev1_tcSPS" cdc="SPS" iedType="RTU560_2">
      <DA name="stVal" bType="BOOLEAN" fc="ST" dchg="true">
        <Val>false</Val>
      </DA>
      <DA name="q" bType="Quality" valKind="RO" fc="ST" qchg="true" />
      <DA name="t" bType="Timestamp" valKind="RO" fc="ST" />
      <DA name="d" bType="VisString255" fc="DC" />
    </DOType>
    <EnumType id="Mod">
      <EnumVal ord="1">on</EnumVal>
      <EnumVal ord="2">blocked</EnumVal>
      <EnumVal ord="3">test</EnumVal>
      <EnumVal ord="4">test/blocked</EnumVal>
      <EnumVal ord="5">off</EnumVal>
    </EnumType>
    <EnumType id="ctlModel">
      <EnumVal ord="0">status-only</EnumVal>
      <EnumVal ord="1">direct-with-normal-security</EnumVal>
      <EnumVal ord="2">sbo-with-normal-security</EnumVal>
      <EnumVal ord="3">direct-with-enhanced-security</EnumVal>
      <EnumVal ord="4">sbo-with-enhanced-security</EnumVal>
    </EnumType>
    <EnumType id="Beh">
      <EnumVal ord="1">on</EnumVal>
      <EnumVal ord="2">blocked</EnumVal>
      <EnumVal ord="3">test</EnumVal>
      <EnumVal ord="4">test/blocked</EnumVal>
      <EnumVal ord="5">off</EnumVal>
    </EnumType>
    <EnumType id="Health">
      <EnumVal ord="1">Ok</EnumVal>
      <EnumVal ord="2">Warning</EnumVal>
      <EnumVal ord="3">Alarm</EnumVal>
    </EnumType>
  </DataTypeTemplates>
</SCL>
```
