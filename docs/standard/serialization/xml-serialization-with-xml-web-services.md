---
title: "使用 XML Web services 进行 XML 序列化"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- XML Web services, XML serialization
- XML serialization, XML Web services
- SOAP, XML serialization
- asmx files
- serialization, SOAP
- XML serialization, attributes
- attributes [.NET Framework], XML serialization
- .asmx files
- encoded XML serialization
- literal XML serialization
- serialization, attributes
ms.assetid: a416192f-8102-458e-bc0a-0b8f3f784da9
caps.latest.revision: 5
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 717bcb6f9f72a728d77e2847096ea558a9c50902
ms.openlocfilehash: 6e84c0f0a1022ff4c4fe5a82d1f40f74b51c0f7c
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="xml-serialization-with-xml-web-services"></a><span data-ttu-id="f32e8-102">使用 XML Web services 进行 XML 序列化</span><span class="sxs-lookup"><span data-stu-id="f32e8-102">XML Serialization with XML Web Services</span></span>
<span data-ttu-id="f32e8-103">XML 序列化是在 XML Web services 体系结构中使用的基础传输机制，由 <xref:System.Xml.Serialization.XmlSerializer> 类执行。</span><span class="sxs-lookup"><span data-stu-id="f32e8-103">XML serialization is the underlying transport mechanism used in the XML Web services architecture, performed by the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span> <span data-ttu-id="f32e8-104">要控制由 XML Web service 生成的 XML，可以对用于创建 XML Web service (.asmx) 的文件的类、返回值、参数和字段应用 [控制 XML 序列化的特性](../../../docs/standard/serialization/attributes-that-control-xml-serialization.md)和 [控制编码的 SOAP 序列化的特性](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)中列出的特性。</span><span class="sxs-lookup"><span data-stu-id="f32e8-104">To control the XML generated by an XML Web service, you can apply the attributes listed in both [Attributes That Control XML Serialization](../../../docs/standard/serialization/attributes-that-control-xml-serialization.md) and [Attributes That Control Encoded SOAP Serialization](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md) to the classes, return values, parameters, and fields of a file used to create an XML Web service (.asmx).</span></span> <span data-ttu-id="f32e8-105">有关创建 XML Web service 的更多信息，请参阅[使用 ASP.NET 生成 XML Web service](http://msdn.microsoft.com/en-us/01dfc27c-c68e-4910-a0aa-5e4c2a766b0c)。</span><span class="sxs-lookup"><span data-stu-id="f32e8-105">For more information about creating an XML Web service, see [Building XML Web Services Using ASP.NET](http://msdn.microsoft.com/en-us/01dfc27c-c68e-4910-a0aa-5e4c2a766b0c).</span></span>  
  
## <a name="literal-and-encoded-styles"></a><span data-ttu-id="f32e8-106">文本样式和编码样式</span><span class="sxs-lookup"><span data-stu-id="f32e8-106">Literal and Encoded Styles</span></span>  
 <span data-ttu-id="f32e8-107">XML Web service 生成的 XML 可以用两种方式设置格式，一种是文本方式，另一种是编码方式，如[自定义 SOAP 消息](http://msdn.microsoft.com/en-us/1d777288-c0d9-4e6a-b638-f010da031952)中所述。</span><span class="sxs-lookup"><span data-stu-id="f32e8-107">The XML generated by an XML Web service can be formatted in either one of two ways, either literal or encoded, as explained in [Customizing SOAP Messages](http://msdn.microsoft.com/en-us/1d777288-c0d9-4e6a-b638-f010da031952).</span></span> <span data-ttu-id="f32e8-108">因此有两组控制 XML 序列化的属性。</span><span class="sxs-lookup"><span data-stu-id="f32e8-108">Therefore there are two sets of attributes that control XML serialization.</span></span> <span data-ttu-id="f32e8-109">[控制 XML 序列化的特性](../../../docs/standard/serialization/attributes-that-control-xml-serialization.md)中列出的属性旨在控制文本样式的 XML。</span><span class="sxs-lookup"><span data-stu-id="f32e8-109">The attributes listed in [Attributes That Control XML Serialization](../../../docs/standard/serialization/attributes-that-control-xml-serialization.md) are designed to control literal style XML.</span></span> <span data-ttu-id="f32e8-110">[控制编码的 SOAP 序列化的特性](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)中列出的特性控制编码样式。</span><span class="sxs-lookup"><span data-stu-id="f32e8-110">The attributes listed in [Attributes That Control Encoded SOAP Serialization](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md) control the encoded style.</span></span> <span data-ttu-id="f32e8-111">通过有选择地应用这些属性，可以调整应用程序，使其返回两种样式或其中一种。</span><span class="sxs-lookup"><span data-stu-id="f32e8-111">By selectively applying these attributes, you can tailor an application to return either, or both styles.</span></span> <span data-ttu-id="f32e8-112">而且，这些特性可以根据需要应用于返回值和参数。</span><span class="sxs-lookup"><span data-stu-id="f32e8-112">Furthermore, these attributes can be applied (as appropriate) to return values and parameters.</span></span>  
  
### <a name="example-of-using-both-styles"></a><span data-ttu-id="f32e8-113">使用两种样式的示例</span><span class="sxs-lookup"><span data-stu-id="f32e8-113">Example of Using Both Styles</span></span>  
 <span data-ttu-id="f32e8-114">创建 XML Web services 时，可以对方法使用两组特性。</span><span class="sxs-lookup"><span data-stu-id="f32e8-114">When you're creating an XML Web service, you can use both sets of attributes on the methods.</span></span> <span data-ttu-id="f32e8-115">在下面的代码示例中，名为 `MyService` 的类包含两种 XML Web services 方法：`MyLiteralMethod` 和 `MyEncodedMethod`。</span><span class="sxs-lookup"><span data-stu-id="f32e8-115">In the following code example, the class named `MyService` contains two XML Web service methods, `MyLiteralMethod` and `MyEncodedMethod`.</span></span> <span data-ttu-id="f32e8-116">这两种方法执行相同的功能，即返回 `Order` 类的实例。</span><span class="sxs-lookup"><span data-stu-id="f32e8-116">Both methods perform the same function: returning an instance of the `Order` class.</span></span> <span data-ttu-id="f32e8-117">在 `Order` 类中，<xref:System.Xml.Serialization.XmlTypeAttribute> 和 <xref:System.Xml.Serialization.SoapTypeAttribute> 特性都应用于 `OrderID` 字段，且这两个特性的 `ElementName` 属性设置为不同的值。</span><span class="sxs-lookup"><span data-stu-id="f32e8-117">In the `Order` class, the <xref:System.Xml.Serialization.XmlTypeAttribute> and the <xref:System.Xml.Serialization.SoapTypeAttribute> attributes are both applied to the `OrderID` field, and both attributes have their `ElementName` property set to different values.</span></span>  
  
 <span data-ttu-id="f32e8-118">要运行此示例，请将代码粘贴到扩展名为 .asmx 的文件中，然后将该文件放入由 Internet 信息服务 (IIS) 管理的虚拟目录中。</span><span class="sxs-lookup"><span data-stu-id="f32e8-118">To run the example, paste the code into a file with an .asmx extension, and place the file into a virtual directory managed by Internet Information Services (IIS).</span></span> <span data-ttu-id="f32e8-119">在 HTML 浏览器（如 Internet Explorer）中键入计算机、虚拟目录和文件的名称。</span><span class="sxs-lookup"><span data-stu-id="f32e8-119">From an HTML browser, such as Internet Explorer, type the name of the computer, virtual directory, and file.</span></span>  
  
```vb  
<%@ WebService Language="VB" Class="MyService" %>  
Imports System  
Imports System.Web.Services  
Imports System.Web.Services.Protocols  
Imports System.Xml.Serialization  
Public Class Order  
    ' Both types of attributes can be applied. Depending on which type  
    ' the method used, either one will affect the call.  
    <SoapElement(ElementName:= "EncodedOrderID"), _  
    XmlElement(ElementName:= "LiteralOrderID")> _  
    public OrderID As String  
End Class  
  
Public Class MyService  
    <WebMethod, SoapDocumentMethod> _  
    public Function MyLiteralMethod() As Order   
        Dim myOrder As Order = New Order()  
        return myOrder  
    End Function  
    <WebMethod, SoapRpcMethod> _  
    public Function MyEncodedMethod() As Order   
        Dim myOrder As Order = New Order()  
        return myOrder  
    End Function  
End Class  
```  
  
```csharp  
<%@ WebService Language="C#" Class="MyService" %>  
using System;  
using System.Web.Services;  
using System.Web.Services.Protocols;  
using System.Xml.Serialization;  
public class Order{  
    // Both types of attributes can be applied. Depending on which type  
    // the method used, either one will affect the call.  
    [SoapElement(ElementName = "EncodedOrderID")]  
    [XmlElement(ElementName = "LiteralOrderID")]  
    public String OrderID;  
}  
public class MyService{  
    [WebMethod][SoapDocumentMethod]  
    public Order MyLiteralMethod(){  
        Order myOrder = new Order();  
        return myOrder;  
    }  
    [WebMethod][SoapRpcMethod]  
    public Order MyEncodedMethod(){  
        Order myOrder = new Order();  
        return myOrder;  
    }  
}  
```  
  
 <span data-ttu-id="f32e8-120">下面的代码示例调用 `MyLiteralMethod`。</span><span class="sxs-lookup"><span data-stu-id="f32e8-120">The following code example calls `MyLiteralMethod`.</span></span> <span data-ttu-id="f32e8-121">会将元素名称更改为“LiteralOrderID”。</span><span class="sxs-lookup"><span data-stu-id="f32e8-121">The element name is changed to "LiteralOrderID".</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">  
    <soap:Body>  
        <MyLiteralMethodResponse xmlns="http://tempuri.org/">  
            <MyLiteralMethodResult>  
                <LiteralOrderID>string</LiteralOrderID>  
            </MyLiteralMethodResult>  
        </MyLiteralMethodResponse>  
    </soap:Body>  
</soap:Envelope>  
```  
  
 <span data-ttu-id="f32e8-122">下面的代码示例调用 `MyEncodedMethod`。</span><span class="sxs-lookup"><span data-stu-id="f32e8-122">The following code example calls `MyEncodedMethod`.</span></span> <span data-ttu-id="f32e8-123">元素名称为“EncodedOrderID”。</span><span class="sxs-lookup"><span data-stu-id="f32e8-123">The element name is "EncodedOrderID".</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soapenc="http://schemas.xmlsoap.org/soap/encoding/" xmlns:tns="http://tempuri.org/" xmlns:types="http://tempuri.org/encodedTypes" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">  
    <soap:Body soap:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
        <tns:MyEncodedMethodResponse>  
            <MyEncodedMethodResult href="#id1" />  
        </tns:MyEncodedMethodResponse>  
        <types:Order id="id1" xsi:type="types:Order">  
            <EncodedOrderID xsi:type="xsd:string">string</EncodedOrderID>  
        </types:Order>  
    </soap:Body>  
</soap:Envelope>  
```  
  
### <a name="applying-attributes-to-return-values"></a><span data-ttu-id="f32e8-124">将特性应用于返回值</span><span class="sxs-lookup"><span data-stu-id="f32e8-124">Applying Attributes to Return Values</span></span>  
 <span data-ttu-id="f32e8-125">您还可以将特性应用于返回值，以控制命名空间和元素名称等。</span><span class="sxs-lookup"><span data-stu-id="f32e8-125">You can also apply attributes to return values to control the namespace, element name, and so forth.</span></span> <span data-ttu-id="f32e8-126">下面的代码示例将 `XmlElementAttribute` 特性应用于 `MyLiteralMethod` 方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="f32e8-126">The following code example applies the `XmlElementAttribute` attribute to the return value of the `MyLiteralMethod` method.</span></span> <span data-ttu-id="f32e8-127">这样可让您控制命名空间和元素名称。</span><span class="sxs-lookup"><span data-stu-id="f32e8-127">Doing so allows you to control the namespace and element name.</span></span>  
  
```vb  
<WebMethod, SoapDocumentMethod> _  
public Function MyLiteralMethod() As _  
<XmlElement(Namespace:="http://www.cohowinery.com", _  
ElementName:= "BookOrder")> _  
Order   
    Dim myOrder As Order = New Order()  
    return myOrder  
End Function  
```  
  
```csharp  
[return: XmlElement(Namespace = "http://www.cohowinery.com",  
ElementName = "BookOrder")]  
[WebMethod][SoapDocumentMethod]  
public Order MyLiteralMethod(){  
    Order myOrder = new Order();  
    return myOrder;  
}  
```  
  
 <span data-ttu-id="f32e8-128">代码被调用时，将返回类似如下所示的 XML。</span><span class="sxs-lookup"><span data-stu-id="f32e8-128">When invoked, the code returns XML that resembles the following.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">  
    <soap:Body>  
        <MyLiteralMethodResponse xmlns="http://tempuri.org/">  
            <BookOrder xmlns="http://www.cohowinery.com">  
                <LiteralOrderID>string</LiteralOrderID>  
            </BookOrder>  
        </MyLiteralMethodResponse>  
    </soap:Body>  
</soap:Envelope>  
```  
  
### <a name="attributes-applied-to-parameters"></a><span data-ttu-id="f32e8-129">应用于参数的特性</span><span class="sxs-lookup"><span data-stu-id="f32e8-129">Attributes Applied to Parameters</span></span>  
 <span data-ttu-id="f32e8-130">您还可以将属性应用于参数，以指定命名空间和元素名称等。</span><span class="sxs-lookup"><span data-stu-id="f32e8-130">You can also apply attributes to parameters to specify namespace, element name and so forth.</span></span> <span data-ttu-id="f32e8-131">下面的代码示例向 `MyLiteralMethodResponse` 方法中添加一个参数，并将 `XmlAttributeAttribute` 特性应用于该参数。</span><span class="sxs-lookup"><span data-stu-id="f32e8-131">The following code example adds a parameter to the `MyLiteralMethodResponse` method, and applies the `XmlAttributeAttribute` attribute to the parameter.</span></span> <span data-ttu-id="f32e8-132">为该参数设置了元素名称和命名空间。</span><span class="sxs-lookup"><span data-stu-id="f32e8-132">The element name and namespace are both set for the parameter.</span></span>  
  
```vb  
<WebMethod, SoapDocumentMethod> _  
public Function MyLiteralMethod(<XmlElement _  
("MyOrderID", Namespace:="http://www.microsoft.com")>ID As String) As _  
<XmlElement(Namespace:="http://www.cohowinery.com", _  
ElementName:= "BookOrder")> _  
Order   
    Dim myOrder As Order = New Order()  
    myOrder.OrderID = ID  
    return myOrder  
End Function  
```  
  
```csharp  
[return: XmlElement(Namespace = "http://www.cohowinery.com",  
ElementName = "BookOrder")]  
[WebMethod][SoapDocumentMethod]  
public Order MyLiteralMethod([XmlElement("MyOrderID",   
Namespace="http://www.microsoft.com")] string ID){  
    Order myOrder = new Order();  
    myOrder.OrderID = ID;  
    return myOrder;  
}   
```  
  
 <span data-ttu-id="f32e8-133">SOAP 请求会类似于：</span><span class="sxs-lookup"><span data-stu-id="f32e8-133">The SOAP request would resemble the following.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">  
    <soap:Body>  
        <MyLiteralMethod xmlns="http://tempuri.org/">  
            <MyOrderID xmlns="http://www.microsoft.com">string</MyOrderID>  
        </MyLiteralMethod>  
    </soap:Body>  
</soap:Envelope>  
```  
  
### <a name="applying-attributes-to-classes"></a><span data-ttu-id="f32e8-134">将特性应用于类</span><span class="sxs-lookup"><span data-stu-id="f32e8-134">Applying Attributes to Classes</span></span>  
 <span data-ttu-id="f32e8-135">如果需要控制与类相关联的元素的命名空间，则可以根据需要应用 `XmlTypeAttribute`、`XmlRootAttribute` 和 `SoapTypeAttribute`。</span><span class="sxs-lookup"><span data-stu-id="f32e8-135">If you need to control the namespace of elements that correlate to classes, you can apply `XmlTypeAttribute`, `XmlRootAttribute`, and `SoapTypeAttribute`, as appropriate.</span></span> <span data-ttu-id="f32e8-136">下面的代码示例将这三者全部应用于 `Order` 类。</span><span class="sxs-lookup"><span data-stu-id="f32e8-136">The following code example applies all three to the `Order` class.</span></span>  
  
```vb  
<XmlType("BigBookService"), _  
SoapType("SoapBookService"), _  
XmlRoot("BookOrderForm")> _  
Public Class Order  
    ' Both types of attributes can be applied. Depending on which  
    ' the method used, either one will affect the call.  
    <SoapElement(ElementName:= "EncodedOrderID"), _  
    XmlElement(ElementName:= "LiteralOrderID")> _  
    public OrderID As String  
End Class  
```  
  
```csharp  
[XmlType("BigBooksService", Namespace = "http://www.cpandl.com")]  
[SoapType("SoapBookService")]  
[XmlRoot("BookOrderForm")]  
public class Order{  
    // Both types of attributes can be applied. Depending on which  
    // the method used, either one will affect the call.  
    [SoapElement(ElementName = "EncodedOrderID")]  
    [XmlElement(ElementName = "LiteralOrderID")]  
    public String OrderID;  
}  
```  
  
 <span data-ttu-id="f32e8-137">检查服务说明时，可以看见 `XmlTypeAttribute` 和 `SoapTypeAttribute` 的应用结果，如下面的代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="f32e8-137">The results of applying the `XmlTypeAttribute` and `SoapTypeAttribute` can be seen when you examine the service description, as shown in the following code example.</span></span>  
  
```xml  
    <s:element name="BookOrderForm" type="s0:BigBookService" />   
- <s:complexType name="BigBookService">  
- <s:sequence>  
    <s:element minOccurs="0" maxOccurs="1" name="LiteralOrderID" type="s:string" />   
    </s:sequence>  
  
- <s:schema targetNamespace="http://tempuri.org/encodedTypes">  
- <s:complexType name="SoapBookService">  
- <s:sequence>  
    <s:element minOccurs="1" maxOccurs="1" name="EncodedOrderID" type="s:string" />   
    </s:sequence>  
    </s:complexType>  
    </s:schema>  
```  
  
 <span data-ttu-id="f32e8-138">`XmlRootAttribute` 的作用也可以在 HTTP GET 和 HTTP POST 结果中看见，如下所示。</span><span class="sxs-lookup"><span data-stu-id="f32e8-138">The effect of the `XmlRootAttribute` can also be seen in the HTTP GET and HTTP POST results, as follows.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<BookOrderForm xmlns="http://tempuri.org/">  
    <LiteralOrderID>string</LiteralOrderID>  
</BookOrderForm>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f32e8-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f32e8-139">See Also</span></span>  
 <span data-ttu-id="f32e8-140">[XML 和 SOAP 序列化](../../../docs/standard/serialization/xml-and-soap-serialization.md) </span><span class="sxs-lookup"><span data-stu-id="f32e8-140">[XML and SOAP Serialization](../../../docs/standard/serialization/xml-and-soap-serialization.md) </span></span>  
 <span data-ttu-id="f32e8-141">[控制编码的 SOAP 序列化的特性](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md) </span><span class="sxs-lookup"><span data-stu-id="f32e8-141">[Attributes That Control Encoded SOAP Serialization](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md) </span></span>  
 <span data-ttu-id="f32e8-142">[如何：将对象序列化为 SOAP 编码的 XML 流](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) </span><span class="sxs-lookup"><span data-stu-id="f32e8-142">[How to: Serialize an Object as a SOAP-Encoded XML Stream](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) </span></span>  
 <span data-ttu-id="f32e8-143">[如何：重写编码的 SOAP XML 序列化](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md) </span><span class="sxs-lookup"><span data-stu-id="f32e8-143">[How to: Override Encoded SOAP XML Serialization](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md) </span></span>  
 <span data-ttu-id="f32e8-144">[XML 序列化简介](../../../docs/standard/serialization/introducing-xml-serialization.md) </span><span class="sxs-lookup"><span data-stu-id="f32e8-144">[Introducing XML Serialization](../../../docs/standard/serialization/introducing-xml-serialization.md) </span></span>  
 <span data-ttu-id="f32e8-145">[如何：序列化对象](../../../docs/standard/serialization/how-to-serialize-an-object.md) </span><span class="sxs-lookup"><span data-stu-id="f32e8-145">[How to: Serialize an Object](../../../docs/standard/serialization/how-to-serialize-an-object.md) </span></span>  
 [<span data-ttu-id="f32e8-146">如何：反序列化对象</span><span class="sxs-lookup"><span data-stu-id="f32e8-146">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
