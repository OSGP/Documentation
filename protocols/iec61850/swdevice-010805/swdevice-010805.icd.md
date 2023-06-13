<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# SWDevice-010805.icd

```markup
<?xml version="1.0" encoding="UTF-8"?>
<!--Created by Test with OMICRON IEDScout 4.10 licensed to OMICRON electronics-->
<!--SCL Schema Version 3.1 (2012/10/22)-->
<SCL version="2007" revision="B" xmlns="http://www.iec.ch/61850/2003/SCL" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.iec.ch/61850/2003/SCL SCL.xsd">
    <Header id="" version="" revision="" toolID="OMICRON IEDScout" nameStructure="IEDName" />
    <Communication>
        <SubNetwork name="NONE" type="8-MMS">
            <ConnectedAP iedName="SWDevice" apName="P1">
                <Address>
                    <P type="IP" xsi:type="tP_IP">192.168.105.190</P>
                    <P type="OSI-TSEL" xsi:type="tP_OSI-TSEL">0001</P>
                    <P type="OSI-SSEL" xsi:type="tP_OSI-SSEL">0001</P>
                    <P type="OSI-PSEL" xsi:type="tP_OSI-PSEL">00000001</P>
                    <P type="OSI-AP-Title">1,1,1,999,1</P>
                    <P type="OSI-AP-Invoke" xsi:type="tP_OSI-AP-Invoke">0</P>
                    <P type="OSI-AE-Qualifier" xsi:type="tP_OSI-AE-Qualifier">12</P>
                    <P type="OSI-AE-Invoke" xsi:type="tP_OSI-AE-Invoke">0</P>
                    <P type="MMS-Port" xsi:type="tP_MMS-Port">102</P>
                </Address>
            </ConnectedAP>
        </SubNetwork>
    </Communication>
    <IED name="SWDevice">
        <Services>
            <DynAssociation />
            <GetDirectory />
            <GetDataObjectDefinition />
            <DataObjectDirectory />
            <GetDataSetValue />
            <SetDataSetValue />
            <DataSetDirectory />
            <ConfDataSet max="1" modify="false" />
            <DynDataSet max="42" />
            <ReadWrite />
            <ConfReportControl max="1" bufConf="false" />
            <GetCBValues />
            <ReportSettings rptID="Dyn" optFields="Dyn" bufTime="Dyn" trgOps="Dyn" intgPd="Dyn" owner="true" />
            <ConfLNs fixPrefix="true" fixLnInst="true" />
            <GOOSE max="0" />
            <GSSE max="0" />
        </Services>
        <AccessPoint name="P1">
            <Server>
                <Authentication none="true" />
                <LDevice inst="GenericIO">
                    <LN0 lnType="SWDeviceGenericIO.LLN0" lnClass="LLN0" inst="">
                        <DataSet name="evn_rpn">
                            <FCDA ldInst="GenericIO" prefix="" lnClass="CSLC" lnInst="" doName="EvnRpn" fc="ST" />
                        </DataSet>
                        <ReportControl name="evn_rpn01" rptID="evn_rpn" buffered="true" bufTime="50" datSet="evn_rpn" intgPd="1000" confRev="1">
                            <TrgOps dchg="true" qchg="false" dupd="false" period="false" gi="true" />
                            <OptFields seqNum="true" timeStamp="true" dataSet="true" reasonCode="true" dataRef="false" entryID="true" configRef="false" />
                            <RptEnabled max="1" />
                        </ReportControl>
                        <DOI name="Mod">
                            <DAI name="ctlModel">
                                <Val>status-only</Val>
                            </DAI>
                        </DOI>
                        <DOI name="NamPlt">
                            <DAI name="vendor">
                                <Val>MZ Automation</Val>
                            </DAI>
                            <DAI name="swRev">
                                <Val>0.0.1</Val>
                            </DAI>
                            <DAI name="d">
                                <Val>libiec61850 server example</Val>
                            </DAI>
                            <DAI name="configRev">
                                <Val></Val>
                            </DAI>
                            <DAI name="ldNs">
                                <Val></Val>
                            </DAI>
                        </DOI>
                    </LN0>
                    <LN lnType="SWDeviceGenericIO.CSLC" lnClass="CSLC" inst="">
                        <DOI name="RbOper">
                            <DAI name="ctlModel">
                                <Val>status-only</Val>
                            </DAI>
                        </DOI>
                        <DOI name="TlsCf">
                            <DAI name="enbTls">
                                <Val>0</Val>
                            </DAI>
                            <DAI name="port">
                                <Val>0</Val>
                            </DAI>
                            <DAI name="comName">
                                <Val></Val>
                            </DAI>
                        </DOI>
                        <DOI name="Sensor">
                            <DAI name="ctlModel">
                                <Val>status-only</Val>
                            </DAI>
                        </DOI>
                        <DOI name="Atnm">
                            <DAI name="lon">
                                <Val>5.591</Val>
                            </DAI>
                            <DAI name="lat">
                                <Val>52.143</Val>
                            </DAI>
                            <DAI name="zenith">
                                <Val>0</Val>
                            </DAI>
                        </DOI>
                        <DOI name="SWCf">
                            <DAI name="LT">
                                <Val>RELAY</Val>
                            </DAI>
                            <DAI name="adSetOft">
                                <Val>0</Val>
                            </DAI>
                            <DAI name="adRiseOft">
                                <Val>0</Val>
                            </DAI>
                        </DOI>
                        <DOI name="FuncFwDw">
                            <DAI name="url">
                                <Val></Val>
                            </DAI>
                        </DOI>
                        <DOI name="Clock">
                            <DAI name="tZ">
                                <Val>60</Val>
                            </DAI>
                            <DAI name="dstBegT">
                                <Val>M3.5.0/2</Val>
                            </DAI>
                            <DAI name="dstEndT">
                                <Val>M10.5.0/3</Val>
                            </DAI>
                            <DAI name="dvt">
                                <Val>60</Val>
                            </DAI>
                            <DAI name="enbDst">
                                <Val>1</Val>
                            </DAI>
                            <DAI name="enbNtpC">
                                <Val>1</Val>
                            </DAI>
                            <DAI name="ntpSvrA">
                                <Val>192.168.105.200</Val>
                            </DAI>
                            <DAI name="syncPer">
                                <Val>1440</Val>
                            </DAI>
                            <DAI name="minOst">
                                <Val>2</Val>
                            </DAI>
                            <DAI name="almOst">
                                <Val>5</Val>
                            </DAI>
                            <DAI name="maxOst">
                                <Val>900</Val>
                            </DAI>
                        </DOI>
                        <DOI name="Reg">
                            <DAI name="svrAddr">
                                <Val>10.2.1.127</Val>
                            </DAI>
                            <DAI name="svrPort">
                                <Val>50000</Val>
                            </DAI>
                            <DAI name="ntfEnb">
                                <Val>1</Val>
                            </DAI>
                        </DOI>
                        <DOI name="Log">
                            <DAI name="enb">
                                <Val>1</Val>
                            </DAI>
                        </DOI>
                        <DOI name="ScyFwDw">
                            <DAI name="url">
                                <Val> </Val>
                            </DAI>
                        </DOI>
                        <DOI name="CARepl">
                            <DAI name="url">
                                <Val> </Val>
                            </DAI>
                        </DOI>
                        <DOI name="IPCf">
                            <DAI name="enbDHCP">
                                <Val>1</Val>
                            </DAI>
                            <DAI name="ipAddr">
                                <Val>192.168.105.227</Val>
                            </DAI>
                            <DAI name="netmask">
                                <Val>255.255.255.0</Val>
                            </DAI>
                            <DAI name="gateway">
                                <Val>192.168.1.1</Val>
                            </DAI>
                        </DOI>
                        <DOI name="EvnBuf">
                            <DAI name="enbEvnType">
                                <Val>1FFFFFF</Val>
                            </DAI>
                        </DOI>
                        <DOI name="SNMPCf">
                            <DAI name="userName">
                                <Val>sw_device</Val>
                            </DAI>
                            <DAI name="authKey">
                                <Val>1qaz2wsx</Val>
                            </DAI>
                            <DAI name="encryptKey">
                                <Val>1qaz2wsx</Val>
                            </DAI>
                        </DOI>
                    </LN>
                    <LN lnType="SWDeviceGenericIO.LPHD" lnClass="LPHD" inst="">
                        <DOI name="PhyNam">
                            <DAI name="vendor">
                                <Val>KAI</Val>
                            </DAI>
                            <DAI name="hwRev">
                                <Val>V3.0</Val>
                            </DAI>
                            <DAI name="serNum">
                                <Val>000000000000000000</Val>
                            </DAI>
                            <DAI name="model">
                                <Val>2016-xx-xx</Val>
                            </DAI>
                            <DAI name="name">
                                <Val>AS101</Val>
                            </DAI>
                            <DAI name="msn">
                                <Val>W0000000000000000</Val>
                            </DAI>
                        </DOI>
                    </LN>
                    <LN lnType="SWDeviceGenericIO.XSWC1" lnClass="XSWC" inst="1">
                        <DOI name="SwType">
                            <DAI name="ctlModel">
                                <Val>status-only</Val>
                            </DAI>
                        </DOI>
                        <DOI name="Pos">
                            <DAI name="ctlModel">
                                <Val>status-only</Val>
                            </DAI>
                        </DOI>
                        <DOI name="CfSt">
                            <DAI name="enbOper">
                                <Val>1</Val>
                            </DAI>
                        </DOI>
                        <DOI name="Sche">
                            <SDI name="sche1">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche2">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche3">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche4">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche5">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche6">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche7">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche8">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche9">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche10">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche11">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche12">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche13">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche14">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche15">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche16">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche17">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche18">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche19">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche20">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche21">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche22">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche23">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche24">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche25">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche26">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche27">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche28">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche29">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche30">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche31">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche32">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche33">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche34">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche35">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche36">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche37">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche38">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche39">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche40">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche41">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche42">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche43">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche44">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche45">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche46">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche47">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche48">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche49">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche50">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche51">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche52">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche53">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche54">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche55">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche56">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche57">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche58">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche59">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche60">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche61">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche62">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche63">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche64">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                        </DOI>
                    </LN>
                    <LN lnType="SWDeviceGenericIO.XSWC1" lnClass="XSWC" inst="2">
                        <DOI name="SwType">
                            <DAI name="ctlModel">
                                <Val>status-only</Val>
                            </DAI>
                        </DOI>
                        <DOI name="Pos">
                            <DAI name="ctlModel">
                                <Val>status-only</Val>
                            </DAI>
                        </DOI>
                        <DOI name="CfSt">
                            <DAI name="enbOper">
                                <Val>1</Val>
                            </DAI>
                        </DOI>
                        <DOI name="Sche">
                            <SDI name="sche1">
                                <DAI name="enable">
                                    <Val>1</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>1</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>2</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche2">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche3">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche4">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche5">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche6">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche7">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche8">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche9">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche10">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche11">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche12">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche13">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche14">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche15">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche16">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche17">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche18">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche19">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche20">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche21">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche22">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche23">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche24">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche25">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche26">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche27">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche28">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche29">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche30">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche31">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche32">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche33">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche34">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche35">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche36">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche37">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche38">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche39">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche40">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche41">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche42">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche43">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche44">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche45">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche46">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche47">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche48">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche49">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche50">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche51">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche52">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche53">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche54">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche55">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche56">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche57">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche58">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche59">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche60">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche61">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche62">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche63">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche64">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                        </DOI>
                    </LN>
                    <LN lnType="SWDeviceGenericIO.XSWC1" lnClass="XSWC" inst="3">
                        <DOI name="SwType">
                            <DAI name="ctlModel">
                                <Val>status-only</Val>
                            </DAI>
                        </DOI>
                        <DOI name="Pos">
                            <DAI name="ctlModel">
                                <Val>status-only</Val>
                            </DAI>
                        </DOI>
                        <DOI name="CfSt">
                            <DAI name="enbOper">
                                <Val>1</Val>
                            </DAI>
                        </DOI>
                        <DOI name="Sche">
                            <SDI name="sche1">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche2">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche3">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche4">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche5">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche6">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche7">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche8">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche9">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche10">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche11">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche12">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche13">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche14">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche15">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche16">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche17">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche18">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche19">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche20">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche21">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche22">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche23">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche24">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche25">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche26">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche27">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche28">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche29">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche30">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche31">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche32">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche33">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche34">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche35">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche36">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche37">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche38">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche39">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche40">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche41">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche42">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche43">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche44">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche45">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche46">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche47">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche48">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche49">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche50">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche51">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche52">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche53">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche54">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche55">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche56">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche57">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche58">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche59">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche60">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche61">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche62">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche63">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche64">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                        </DOI>
                    </LN>
                    <LN lnType="SWDeviceGenericIO.XSWC1" lnClass="XSWC" inst="4">
                        <DOI name="SwType">
                            <DAI name="ctlModel">
                                <Val>status-only</Val>
                            </DAI>
                        </DOI>
                        <DOI name="Pos">
                            <DAI name="ctlModel">
                                <Val>status-only</Val>
                            </DAI>
                        </DOI>
                        <DOI name="CfSt">
                            <DAI name="enbOper">
                                <Val>1</Val>
                            </DAI>
                        </DOI>
                        <DOI name="Sche">
                            <SDI name="sche1">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche2">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche3">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche4">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche5">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche6">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche7">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche8">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche9">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche10">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche11">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche12">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche13">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche14">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche15">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche16">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche17">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche18">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche19">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche20">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche21">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche22">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche23">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche24">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche25">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche26">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche27">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche28">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche29">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche30">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche31">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche32">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche33">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche34">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche35">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche36">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche37">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche38">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche39">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche40">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche41">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche42">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche43">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche44">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche45">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche46">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche47">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche48">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche49">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche50">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche51">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche52">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche53">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche54">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche55">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche56">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche57">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche58">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche59">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche60">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche61">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche62">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche63">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                            <SDI name="sche64">
                                <DAI name="enable">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="day">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOn">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOnT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOff">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="tOffT">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="minOnPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="minOffPer">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srBefWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="srAftWd">
                                    <Val>30</Val>
                                </DAI>
                                <DAI name="igBefWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="igAftWd">
                                    <Val>0</Val>
                                </DAI>
                                <DAI name="Descr">
                                    <Val>ON/OFF schedule</Val>
                                </DAI>
                            </SDI>
                        </DOI>
                    </LN>
                </LDevice>
            </Server>
        </AccessPoint>
    </IED>
    <DataTypeTemplates>
        <LNodeType id="SWDeviceGenericIO.CSLC" lnClass="CSLC">
            <DO name="RbOper" type="SWDeviceGenericIO.CSLC.RbOper" />
            <DO name="TlsCf" type="SWDeviceGenericIO.CSLC.TlsCf" />
            <DO name="Sensor" type="SWDeviceGenericIO.CSLC.Sensor" />
            <DO name="Atnm" type="SWDeviceGenericIO.CSLC.Atnm" />
            <DO name="SWCf" type="SWDeviceGenericIO.CSLC.SWCf" />
            <DO name="FuncFwDw" type="SWDeviceGenericIO.CSLC.FuncFwDw" />
            <DO name="Clock" type="SWDeviceGenericIO.CSLC.Clock" />
            <DO name="Reg" type="SWDeviceGenericIO.CSLC.Reg" />
            <DO name="Log" type="SWDeviceGenericIO.CSLC.Log" />
            <DO name="ScyFwDw" type="SWDeviceGenericIO.CSLC.FuncFwDw" />
            <DO name="CARepl" type="SWDeviceGenericIO.CSLC.FuncFwDw" />
            <DO name="IPCf" type="SWDeviceGenericIO.CSLC.IPCf" />
            <DO name="EvnRpn" type="SWDeviceGenericIO.CSLC.EvnRpn" />
            <DO name="EvnBuf" type="SWDeviceGenericIO.CSLC.EvnBuf" />
            <DO name="SNMPCf" type="SWDeviceGenericIO.CSLC.SNMPCf" />
        </LNodeType>
        <LNodeType id="SWDeviceGenericIO.XSWC1" lnClass="XSWC">
            <DO name="OpCnt" type="SWDeviceGenericIO.XSWC1.OpCnt" />
            <DO name="SwType" type="SWDeviceGenericIO.XSWC1.SwType" />
            <DO name="Pos" type="SWDeviceGenericIO.CSLC.Sensor" />
            <DO name="OnItvB" type="SWDeviceGenericIO.XSWC1.OnItvB" />
            <DO name="CfSt" type="SWDeviceGenericIO.XSWC1.CfSt" />
            <DO name="Sche" type="SWDeviceGenericIO.XSWC1.Sche" />
        </LNodeType>
        <LNodeType id="SWDeviceGenericIO.LLN0" lnClass="LLN0">
            <DO name="Beh" type="SWDeviceGenericIO.LLN0.Beh" />
            <DO name="Health" type="SWDeviceGenericIO.LLN0.Health" />
            <DO name="Mod" type="SWDeviceGenericIO.LLN0.Mod" />
            <DO name="NamPlt" type="SWDeviceGenericIO.LLN0.NamPlt" />
        </LNodeType>
        <LNodeType id="SWDeviceGenericIO.LPHD" lnClass="LPHD">
            <DO name="PhyHealth" type="SWDeviceGenericIO.LLN0.Health" />
            <DO name="Proxy" type="SWDeviceGenericIO.LPHD.Proxy" />
            <DO name="PhyNam" type="SWDeviceGenericIO.LPHD.PhyNam" />
        </LNodeType>
        <DOType id="SWDeviceGenericIO.CSLC.TlsCf" cdc="UNKNOWN">
            <DA name="enbTls" fc="CF" bType="BOOLEAN" />
            <DA name="port" fc="CF" bType="INT32U" />
            <DA name="comName" fc="CF" bType="VisString255" />
        </DOType>
        <DOType id="SWDeviceGenericIO.CSLC.Atnm" cdc="UNKNOWN">
            <DA name="sunset" fc="ST" bType="Timestamp" />
            <DA name="sunrise" fc="ST" bType="Timestamp" />
            <DA name="lon" fc="CF" bType="FLOAT32" />
            <DA name="lat" fc="CF" bType="FLOAT32" />
            <DA name="zenith" fc="CF" bType="INT8U" />
        </DOType>
        <DOType id="SWDeviceGenericIO.CSLC.SWCf" cdc="UNKNOWN">
            <DA name="LT" fc="CF" bType="VisString64" />
            <DA name="adSetOft" fc="CF" bType="INT16" />
            <DA name="adRiseOft" fc="CF" bType="INT16" />
        </DOType>
        <DOType id="SWDeviceGenericIO.CSLC.FuncFwDw" cdc="UNKNOWN">
            <DA name="status" fc="ST" bType="INT8" />
            <DA name="curVer" fc="ST" bType="VisString32" />
            <DA name="url" fc="CF" bType="VisString255" />
            <DA name="startT" fc="CF" bType="Timestamp" />
        </DOType>
        <DOType id="SWDeviceGenericIO.CSLC.Clock" cdc="UNKNOWN">
            <DA name="curT" fc="CF" bType="Timestamp" />
            <DA name="tZ" fc="CF" bType="INT16" />
            <DA name="dstBegT" fc="CF" bType="VisString255" />
            <DA name="dstEndT" fc="CF" bType="VisString255" />
            <DA name="dvt" fc="CF" bType="INT16" />
            <DA name="enbDst" fc="CF" bType="BOOLEAN" />
            <DA name="enbNtpC" fc="CF" bType="BOOLEAN" />
            <DA name="ntpSvrA" fc="CF" bType="VisString255" />
            <DA name="syncPer" fc="CF" bType="INT16U" />
            <DA name="minOst" fc="CF" bType="INT16U" />
            <DA name="almOst" fc="CF" bType="INT16U" />
            <DA name="maxOst" fc="CF" bType="INT16U" />
        </DOType>
        <DOType id="SWDeviceGenericIO.CSLC.Reg" cdc="UNKNOWN">
            <DA name="svrAddr" fc="CF" bType="VisString64" />
            <DA name="svrPort" fc="CF" bType="INT32" />
            <DA name="ntfEnb" fc="CF" bType="BOOLEAN" />
        </DOType>
        <DOType id="SWDeviceGenericIO.CSLC.Log" cdc="UNKNOWN">
            <DA name="enb" fc="CF" bType="BOOLEAN" />
        </DOType>
        <DOType id="SWDeviceGenericIO.CSLC.IPCf" cdc="UNKNOWN">
            <DA name="mac" fc="ST" bType="VisString32" />
            <DA name="enbDHCP" fc="CF" bType="BOOLEAN" />
            <DA name="ipAddr" fc="CF" bType="VisString32" />
            <DA name="netmask" fc="CF" bType="VisString32" />
            <DA name="gateway" fc="CF" bType="VisString32" />
        </DOType>
        <DOType id="SWDeviceGenericIO.CSLC.EvnRpn" cdc="UNKNOWN">
            <DA name="evnType" fc="ST" bType="INT8U" />
            <DA name="swNum" fc="ST" bType="INT8U" />
            <DA name="trgType" fc="ST" bType="INT8U" />
            <DA name="swVal" fc="ST" bType="BOOLEAN" />
            <DA name="trgTime" fc="ST" bType="Timestamp" />
            <DA name="remark" fc="ST" bType="VisString64" />
        </DOType>
        <DOType id="SWDeviceGenericIO.CSLC.EvnBuf" cdc="UNKNOWN">
            <DA name="lastIdx" fc="ST" bType="INT16U" />
            <DA name="evn1" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn2" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn3" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn4" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn5" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn6" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn7" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn8" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn9" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn10" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn11" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn12" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn13" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn14" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn15" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn16" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn17" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn18" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn19" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn20" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn21" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn22" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn23" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn24" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn25" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn26" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn27" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn28" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn29" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn30" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn31" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn32" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn33" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn34" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn35" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn36" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn37" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn38" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn39" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn40" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn41" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn42" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn43" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn44" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn45" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn46" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn47" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn48" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn49" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn50" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn51" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn52" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn53" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn54" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn55" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn56" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn57" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn58" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn59" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn60" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn61" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn62" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn63" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn64" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn65" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn66" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn67" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn68" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn69" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn70" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn71" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn72" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn73" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn74" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn75" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn76" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn77" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn78" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn79" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn80" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn81" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn82" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn83" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn84" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn85" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn86" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn87" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn88" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn89" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn90" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn91" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn92" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn93" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn94" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn95" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn96" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn97" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn98" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn99" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn100" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn101" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn102" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn103" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn104" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn105" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn106" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn107" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn108" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn109" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn110" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn111" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn112" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn113" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn114" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn115" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn116" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn117" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn118" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn119" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="evn120" fc="ST" bType="Struct" type="SWDeviceGenericIO.CSLC.EvnBuf.evn1" />
            <DA name="enbEvnType" fc="CF" bType="VisString32" />
        </DOType>
        <DOType id="SWDeviceGenericIO.CSLC.SNMPCf" cdc="UNKNOWN">
            <DA name="userName" fc="CF" bType="VisString255" />
            <DA name="authKey" fc="CF" bType="VisString255" />
            <DA name="encryptKey" fc="CF" bType="VisString255" />
        </DOType>
        <DOType id="SWDeviceGenericIO.XSWC1.OnItvB" cdc="UNKNOWN">
            <DA name="lastIdx" fc="ST" bType="INT8U" />
            <DA name="itv1" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv2" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv3" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv4" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv5" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv6" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv7" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv8" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv9" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv10" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv11" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv12" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv13" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv14" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv15" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv16" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv17" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv18" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv19" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv20" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv21" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv22" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv23" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv24" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv25" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv26" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv27" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv28" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv29" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv30" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv31" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv32" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv33" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv34" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv35" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv36" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv37" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv38" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv39" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv40" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv41" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv42" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv43" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv44" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv45" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv46" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv47" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv48" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv49" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv50" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv51" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv52" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv53" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv54" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv55" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv56" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv57" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv58" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv59" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
            <DA name="itv60" fc="ST" bType="Struct" type="SWDeviceGenericIO.XSWC1.OnItvB.itv1" />
        </DOType>
        <DOType id="SWDeviceGenericIO.XSWC1.CfSt" cdc="UNKNOWN">
            <DA name="enbOper" fc="CF" bType="BOOLEAN" />
        </DOType>
        <DOType id="SWDeviceGenericIO.XSWC1.Sche" cdc="UNKNOWN">
            <DA name="sche1" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche2" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche3" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche4" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche5" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche6" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche7" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche8" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche9" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche10" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche11" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche12" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche13" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche14" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche15" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche16" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche17" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche18" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche19" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche20" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche21" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche22" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche23" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche24" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche25" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche26" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche27" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche28" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche29" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche30" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche31" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche32" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche33" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche34" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche35" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche36" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche37" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche38" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche39" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche40" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche41" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche42" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche43" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche44" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche45" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche46" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche47" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche48" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche49" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche50" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche51" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche52" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche53" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche54" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche55" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche56" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche57" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche58" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche59" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche60" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche61" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche62" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche63" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
            <DA name="sche64" fc="CF" bType="Struct" type="SWDeviceGenericIO.XSWC1.Sche.sche1" />
        </DOType>
        <DOType id="SWDeviceGenericIO.LPHD.PhyNam" cdc="DPL">
            <DA name="vendor" fc="DC" bType="VisString255" />
            <DA name="hwRev" fc="DC" bType="VisString255" />
            <DA name="serNum" fc="DC" bType="VisString255" />
            <DA name="model" fc="DC" bType="VisString255" />
            <DA name="name" fc="DC" bType="VisString255" />
            <DA name="msn" fc="DC" bType="VisString255" />
        </DOType>
        <DOType id="SWDeviceGenericIO.LLN0.Mod" cdc="INC">
            <DA name="stVal" fc="ST" bType="Enum" type="Mod" />
            <DA name="q" fc="ST" bType="Quality" />
            <DA name="t" fc="ST" bType="Timestamp" />
            <DA name="Oper" fc="CO" bType="Struct" type="SWDeviceGenericIO.LLN0.Mod.Oper" />
            <DA name="ctlModel" fc="CF" bType="Enum" type="ctlModel" />
        </DOType>
        <DOType id="SWDeviceGenericIO.XSWC1.SwType" cdc="INC">
            <DA name="stVal" fc="ST" bType="INT8" />
            <DA name="q" fc="ST" bType="Quality" />
            <DA name="t" fc="ST" bType="Timestamp" />
            <DA name="Oper" fc="CO" bType="Struct" type="SWDeviceGenericIO.XSWC1.SwType.Oper" />
            <DA name="ctlModel" fc="CF" bType="Enum" type="ctlModel" />
        </DOType>
        <DOType id="SWDeviceGenericIO.LLN0.Beh" cdc="INS">
            <DA name="stVal" fc="ST" bType="Enum" type="Beh" />
            <DA name="q" fc="ST" bType="Quality" />
            <DA name="t" fc="ST" bType="Timestamp" />
        </DOType>
        <DOType id="SWDeviceGenericIO.LLN0.Health" cdc="INS">
            <DA name="stVal" fc="ST" bType="Enum" type="Health" />
            <DA name="q" fc="ST" bType="Quality" />
            <DA name="t" fc="ST" bType="Timestamp" />
        </DOType>
        <DOType id="SWDeviceGenericIO.XSWC1.OpCnt" cdc="INS">
            <DA name="stVal" fc="ST" bType="INT32" />
            <DA name="q" fc="ST" bType="Quality" />
            <DA name="t" fc="ST" bType="Timestamp" />
        </DOType>
        <DOType id="SWDeviceGenericIO.LLN0.NamPlt" cdc="LPL">
            <DA name="vendor" fc="DC" bType="VisString255" />
            <DA name="swRev" fc="DC" bType="VisString255" />
            <DA name="d" fc="DC" bType="VisString255" />
            <DA name="configRev" fc="DC" bType="VisString255" />
            <DA name="ldNs" fc="EX" bType="VisString255" />
        </DOType>
        <DOType id="SWDeviceGenericIO.CSLC.RbOper" cdc="SPC">
            <DA name="stVal" fc="ST" bType="BOOLEAN" />
            <DA name="Oper" fc="CO" bType="Struct" type="SWDeviceGenericIO.CSLC.RbOper.Oper" />
            <DA name="ctlModel" fc="CF" bType="Enum" type="ctlModel" />
        </DOType>
        <DOType id="SWDeviceGenericIO.CSLC.Sensor" cdc="SPC">
            <DA name="stVal" fc="ST" bType="BOOLEAN" />
            <DA name="q" fc="ST" bType="Quality" />
            <DA name="t" fc="ST" bType="Timestamp" />
            <DA name="Oper" fc="CO" bType="Struct" type="SWDeviceGenericIO.CSLC.RbOper.Oper" />
            <DA name="ctlModel" fc="CF" bType="Enum" type="ctlModel" />
        </DOType>
        <DOType id="SWDeviceGenericIO.LPHD.Proxy" cdc="SPS">
            <DA name="stVal" fc="ST" bType="BOOLEAN" />
            <DA name="q" fc="ST" bType="Quality" />
            <DA name="t" fc="ST" bType="Timestamp" />
        </DOType>
        <DAType id="SWDeviceGenericIO.CSLC.EvnBuf.evn1">
            <BDA name="evnType" bType="INT8U" />
            <BDA name="swNum" bType="INT8U" />
            <BDA name="trgType" bType="INT8U" />
            <BDA name="swVal" bType="BOOLEAN" />
            <BDA name="trgTime" bType="Timestamp" />
            <BDA name="remark" bType="VisString64" />
        </DAType>
        <DAType id="SWDeviceGenericIO.XSWC1.OnItvB.itv1">
            <BDA name="itv" bType="INT32" />
            <BDA name="day" bType="Timestamp" />
        </DAType>
        <DAType id="SWDeviceGenericIO.XSWC1.Sche.sche1">
            <BDA name="enable" bType="BOOLEAN" />
            <BDA name="day" bType="INT32" />
            <BDA name="tOn" bType="INT32" />
            <BDA name="tOnT" bType="INT8" />
            <BDA name="tOff" bType="INT32" />
            <BDA name="tOffT" bType="INT8" />
            <BDA name="minOnPer" bType="INT16U" />
            <BDA name="minOffPer" bType="INT16U" />
            <BDA name="srBefWd" bType="INT16U" />
            <BDA name="srAftWd" bType="INT16U" />
            <BDA name="igBefWd" bType="INT16U" />
            <BDA name="igAftWd" bType="INT16U" />
            <BDA name="Descr" bType="VisString255" />
        </DAType>
        <DAType id="SWDeviceGenericIO.LLN0.Mod.Oper.origin">
            <BDA name="orCat" bType="Enum" type="orCategory" />
            <BDA name="orIdent" bType="Octet64" />
        </DAType>
        <DAType id="SWDeviceGenericIO.CSLC.RbOper.Oper">
            <BDA name="ctlVal" bType="BOOLEAN" />
            <BDA name="origin" bType="Struct" type="SWDeviceGenericIO.LLN0.Mod.Oper.origin" />
            <BDA name="ctlNum" bType="INT8U" />
            <BDA name="T" bType="Timestamp" />
            <BDA name="Test" bType="BOOLEAN" />
            <BDA name="Check" bType="Check" />
        </DAType>
        <DAType id="SWDeviceGenericIO.LLN0.Mod.Oper">
            <BDA name="ctlVal" bType="Enum" type="Mod" />
            <BDA name="origin" bType="Struct" type="SWDeviceGenericIO.LLN0.Mod.Oper.origin" />
            <BDA name="ctlNum" bType="INT8U" />
            <BDA name="T" bType="Timestamp" />
            <BDA name="Test" bType="BOOLEAN" />
            <BDA name="Check" bType="Check" />
        </DAType>
        <DAType id="SWDeviceGenericIO.XSWC1.SwType.Oper">
            <BDA name="ctlVal" bType="INT8" />
            <BDA name="origin" bType="Struct" type="SWDeviceGenericIO.LLN0.Mod.Oper.origin" />
            <BDA name="ctlNum" bType="INT8U" />
            <BDA name="T" bType="Timestamp" />
            <BDA name="Test" bType="BOOLEAN" />
            <BDA name="Check" bType="Check" />
        </DAType>
        <EnumType id="ctlModel">
            <!--Source: IEC 61850-7-3:2003-->
            <EnumVal ord="0">status-only</EnumVal>
            <EnumVal ord="1">direct-with-normal-security</EnumVal>
            <EnumVal ord="2">sbo-with-normal-security</EnumVal>
            <EnumVal ord="3">direct-with-enhanced-security</EnumVal>
            <EnumVal ord="4">sbo-with-enhanced-security</EnumVal>
        </EnumType>
        <EnumType id="orCategory">
            <!--Source: IEC 61850-7-3:2003-->
            <EnumVal ord="0">not-supported</EnumVal>
            <EnumVal ord="1">bay-control</EnumVal>
            <EnumVal ord="2">station-control</EnumVal>
            <EnumVal ord="3">remote-control</EnumVal>
            <EnumVal ord="4">automatic-bay</EnumVal>
            <EnumVal ord="5">automatic-station</EnumVal>
            <EnumVal ord="6">automatic-remote</EnumVal>
            <EnumVal ord="7">maintenance</EnumVal>
            <EnumVal ord="8">process</EnumVal>
        </EnumType>
        <EnumType id="Beh">
            <!--Source: IEC 61850-7-4:2003-->
            <EnumVal ord="1">on</EnumVal>
            <EnumVal ord="2">blocked</EnumVal>
            <EnumVal ord="3">test</EnumVal>
            <EnumVal ord="4">test/blocked</EnumVal>
            <EnumVal ord="5">off</EnumVal>
        </EnumType>
        <EnumType id="Health">
            <!--Source: IEC 61850-7-4:2003-->
            <EnumVal ord="1">Ok</EnumVal>
            <EnumVal ord="2">Warning</EnumVal>
            <EnumVal ord="3">Alarm</EnumVal>
        </EnumType>
        <EnumType id="Mod">
            <!--Source: IEC 61850-7-4:2003-->
            <EnumVal ord="1">on</EnumVal>
            <EnumVal ord="2">blocked</EnumVal>
            <EnumVal ord="3">test</EnumVal>
            <EnumVal ord="4">test/blocked</EnumVal>
            <EnumVal ord="5">off</EnumVal>
        </EnumType>
    </DataTypeTemplates>
</SCL>
```

