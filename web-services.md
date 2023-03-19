# Web Services

Steps:

- create project -> select -> ASP.NET Web Application (.NET Framework) -> Empty
- right click project -> add item ->select webservices .asmx extension
- right click on solution add new project -> CalculatorWebApplication -> its asp.net web application
- right click reference -> add service reference
Address -> https://localhost:44339/CalculatorWebService.asmx?WSDL
-> namespace -> CalculatorService


WebForm
```
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="WebForm.aspx.cs" Inherits="CalculatorWebApplication.WebForm" %>

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title></title>
</head>
<body>
    <form id="form1" runat="server">
        <table style="font-family">
            <tr>
                <td>
                    <b>First Number</b>
                </td>
                <td>
                    <asp:TextBox ID="txtFirstNumber" runat="server"></asp:TextBox>
                </td>
            </tr>
            <tr>
                <td>
                    <b>Second Number</b>
                </td>
                <td>
                    <asp:TextBox ID="txtSecondNumber" runat="server"></asp:TextBox>
                </td>
            </tr>
            <tr>
                <td>
                    <b>Result</b>
                </td>
                <td>
                    <asp:Label ID="lblResult" runat="server" Text="Label"></asp:Label>
                </td>
            </tr>
            <tr>
                <td colspan="2">
                    <asp:Button ID="btnAdd" runat="server" Text="Add" OnClick="btnAdd_Click" />
                </td>
            </tr>
        </table>
    </form>
</body>
</html>
```

left Design -> to View Form
