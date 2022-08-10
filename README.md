CREATE COMPUTE MODULE Responce_flow_Compute
	CREATE FUNCTION Main() RETURNS BOOLEAN
	BEGIN
		-- CALL CopyMessageHeaders();
		-- CALL CopyEntireMessage();
		DECLARE  resulta, resultm INTEGER;
		SET resulta = InputRoot.SOAP.Body.ns:Request_a.a +  InputRoot.SOAP.Body.ns:Request_a.b;
		SET resultm = InputRoot.SOAP.Body.ns:Request_m.x * InputRoot.SOAP.Body.ns:Request_m.y;
		
		
		SET OutputRoot.XMLNSC.Result."Operation Add".result = resulta;

DECLARE sp1,Operation NAMESPACE 'http://www.ibm.com/space1';


SET OutputRoot.XMLNS.Results.(XML.NamespaceDecl)xmlns:Operation = 'http://www.ibm.com/space1'; 
SET OutputRoot.XMLNS.Results.Operation:add.result = resulta;
SET OutputRoot.XMLNS.Results.Operation:mul.result = resultm;
