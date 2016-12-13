# libfintx

[![Coverage Status](https://coveralls.io/repos/github/mrklintscher/libfintx/badge.svg?branch=master)](https://coveralls.io/github/mrklintscher/libfintx?branch=master)
[![Build Status](https://travis-ci.org/mrklintscher/libfintx.svg?branch=master)](https://travis-ci.org/mrklintscher/libfintx)

An C# based client library for **HBCI 2.2** and **FinTS 3.0**.

In 1995 the ZKA announced a common standardized online banking standard called *Homebanking Computer Interface* (HBCI). In 2003 they published the next generation of this protocol standard and named it *Financial Transaction Services* (FinTS).

Today most of all german banks support this online banking standards.

This client library supports both APIs, HBCI 2.2 and FinTS 3.0.

It can be used to read the balance of a bank account, receive an account statement, and make a SEPA payment using PIN/TAN.

# Usage

There are many reasons why you need to use a banking library which can exchange data from your application with the bank. One reason jfor example is to found a [Fintech](https://de.wikipedia.org/wiki/Finanztechnologie).

# Sample

e.g. read balance

```
public static string Balance(int Account, int BLZ, string IBAN, 
                             string BIC, string URL, int HBCIVersion, int UserID, string PIN)
```

# Features

* Balance (**HKSAL**)
* Transactions (**HKKAZ**)
* Transfer money (**HKCCS**)
* Transfer money at a certain time (**HKCCS**)
* Collect money (**HKDSE**)

# Documentation

```
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>libfintx</name>
    </assembly>
    <members>
        <member name="M:libfintx.Main.Synchronization(System.Int32,System.String,System.Int32,System.Int32,System.String)">
            <summary>
            Synchronize bank connection
            </summary>
            <param name="BLZ"></param>
            <param name="URL"></param>
            <param name="HBCIVersion"></param>
            <param name="UserID"></param>
            <param name="PIN"></param>
            <returns>
            Success or failure
            </returns>
        </member>
        <member name="M:libfintx.Main.Balance(System.Int32,System.Int32,System.String,System.String,System.String,System.Int32,System.Int32,System.String)">
            <summary>
            Account balance
            </summary>
            <param name="Account"></param>
            <param name="BLZ"></param>
            <param name="IBAN"></param>
            <param name="BIC"></param>
            <param name="URL"></param>
            <param name="HBCIVersion"></param>
            <param name="UserID"></param>
            <param name="PIN"></param>
            <returns>
            Balance
            </returns>
        </member>
        <member name="M:libfintx.Main.Transactions(System.Int32,System.Int32,System.String,System.String,System.String,System.Int32,System.Int32,System.String)">
            <summary>
            Account transactions
            </summary>
            <param name="Account"></param>
            <param name="BLZ"></param>
            <param name="IBAN"></param>
            <param name="BIC"></param>
            <param name="URL"></param>
            <param name="HBCIVersion"></param>
            <param name="UserID"></param>
            <param name="PIN"></param>
            <returns>
            Transactions
            </returns>
        </member>
        <member name="M:libfintx.Main.Transfer(System.Int32,System.String,System.String,System.String,System.String,System.String,System.String,System.String,System.String,System.String,System.Int32,System.Int32,System.String,System.String,System.Windows.Forms.PictureBox)">
            <summary>
            Transfer money
            </summary>
            <param name="BLZ"></param>
            <param name="AccountHolder"></param>
            <param name="AccountHolderIBAN"></param>
            <param name="AccountHolderBIC"></param>
            <param name="Receiver"></param>
            <param name="ReceiverIBAN"></param>
            <param name="ReceiverBIC"></param>
            <param name="Amount"></param>
            <param name="Purpose"></param>
            <param name="URL"></param>
            <param name="HBCIVersion"></param>
            <param name="UserID"></param>
            <param name="PIN"></param>
            <param name="HIRMS"></param>
            <param name="pictureBox"></param>
            <returns>
            Bank return codes
            </returns>
        </member>
        <member name="M:libfintx.Main.Transfer_Terminated(System.Int32,System.String,System.String,System.String,System.String,System.String,System.String,System.String,System.String,System.String,System.String,System.Int32,System.Int32,System.String,System.String,System.Windows.Forms.PictureBox)">
            <summary>
            Transfer money at a certain time
            </summary>
            <param name="BLZ"></param>
            <param name="AccountHolder"></param>
            <param name="AccountHolderIBAN"></param>
            <param name="AccountHolderBIC"></param>
            <param name="Receiver"></param>
            <param name="ReceiverIBAN"></param>
            <param name="ReceiverBIC"></param>
            <param name="Amount"></param>
            <param name="Purpose"></param>
            <param name="ExecutionDay"></param>
            <param name="URL"></param>
            <param name="HBCIVersion"></param>
            <param name="UserID"></param>
            <param name="PIN"></param>
            <param name="HIRMS"></param>
            <param name="pictureBox"></param>
            <returns>
            Bank return codes
            </returns>
        </member>
        <member name="M:libfintx.Main.Collect(System.Int32,System.String,System.String,System.String,System.String,System.String,System.String,System.Decimal,System.String,System.String,System.String,System.String,System.String,System.String,System.Int32,System.Int32,System.String,System.String,System.Windows.Forms.PictureBox)">
            <summary>
            Collect money from another account
            </summary>
            <param name="BLZ"></param>
            <param name="AccountHolder"></param>
            <param name="AccountHolderIBAN"></param>
            <param name="AccountHolderBIC"></param>
            <param name="Payer"></param>
            <param name="PayerIBAN"></param>
            <param name="PayerBIC"></param>
            <param name="Amount"></param>
            <param name="Purpose"></param>
            <param name="SettlementDate"></param>
            <param name="MandateNumber"></param>
            <param name="MandateDate"></param>
            <param name="CeditorIDNumber"></param>
            <param name="URL"></param>
            <param name="HBCIVersion"></param>
            <param name="UserID"></param>
            <param name="PIN"></param>
            <param name="HIRMS"></param>
            <param name="pictureBox"></param>
            <returns>
            Bank return codes
            </returns>
        </member>
        <member name="M:libfintx.Main.TAN(System.String,System.String,System.Int32,System.Int32,System.Int32,System.String)">
            <summary>
            Confirm order with TAN
            </summary>
            <param name="TAN"></param>
            <param name="URL"></param>
            <param name="HBCIVersion"></param>
            <param name="BLZ"></param>
            <param name="UserID"></param>
            <param name="PIN"></param>
            <returns>
            Bank return codes
            </returns>
        </member>
        <member name="M:libfintx.Main.TAN_Scheme">
            <summary>
            TAN scheme
            </summary>
            <returns>
            TAN mechanism
            </returns>
        </member>
        <member name="M:libfintx.Main.Assembly(System.String,System.String)">
            <summary>
            Set assembly informations
            </summary>
            <param name="Buildname"></param>
            <param name="Version"></param>
        </member>
        <member name="M:libfintx.Main.Buildname">
            <summary>
            Get assembly buildname
            </summary>
            <returns>
            Buildname
            </returns>
        </member>
        <member name="M:libfintx.Main.Version">
            <summary>
            Get assembly version
            </summary>
            <returns>
            Version
            </returns>
        </member>
        <member name="M:libfintx.Main.Transaction_Output">
            <summary>
            Transactions output console
            </summary>
            <returns>
            Bank return codes
            </returns>
        </member>
    </members>
</doc>
```

# Specification

For exact information please refer to the [German version of the specification](http://www.hbci-zka.de/spec/spezifikation.htm). There is
also an [unauthorized English translation](http://www.hbci-zka.de/english/specification/engl_2_2.htm).

# SSL verification

The verification process is done by using the default **WebRequest** class.

# Copyright & License

Copyright (c) 2016 [Torsten Klinger](http://www.mrklintscher.com)

Licensed under GNU Lesser General Public License. Please read the LICENSE file.
