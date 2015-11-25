# Test

Insert into data

SELECT tag as tag,isnull(cast(nullif(value, 0) as varchar(10)),'')as value, time as time,
	
	(Select case
		when CHARINDEX('P1_AVG',right(tag,6)) = 1 then 'Pressure 1'
		when CHARINDEX('P1_Lo',right(tag,5)) = 1 then 'Pressure 1'
		when CHARINDEX('P1_Hi',right(tag,5)) = 1 then 'Pressure 1'
		when CHARINDEX('P2_AVG',right(tag,6)) = 1 then 'Pressure 2'
		when CHARINDEX('P2_Lo',right(tag,5)) = 1 then 'Pressure 2'
		when CHARINDEX('P2_Hi',right(tag,5)) = 1 then 'Pressure 2' 			
		when CHARINDEX('Batt_Volt', right(tag,9))= 1 then 'Batt Voltage'
		when CHARINDEX('Batt_AVG', right(tag,8))= 1 then 'Batt Voltage'
		when CHARINDEX('Batt_AVE', right(tag,8))= 1 then 'Batt Voltage'
		when CHARINDEX('Temp', right(tag,4))= 1 then 'Temperature'
		when CHARINDEX('RP1_HH', right(tag,6))= 1 then 'P1 MOP Pressure Alarm'
		when CHARINDEX('RP1_H', right(tag,5))= 1 then 'P1 HH Pressure Alarm'
		when CHARINDEX('RP1_L', right(tag,5))= 1 then 'P1 L Pressure Alarm'
		when CHARINDEX('RP1_LL', right(tag,6))= 1 then 'P1 LL Pressure Alarm'
		when CHARINDEX('RP2_HH', right(tag,6))= 1 then 'P2 MOP Pressure Alarm'
		when CHARINDEX('RP2_H', right(tag,5))= 1 then 'P2 HH Pressure Alarm'
		when CHARINDEX('RP2_L', right(tag,5))= 1 then 'P2 L Pressure Alarm'
		when CHARINDEX('RP2_LL', right(tag,6))= 1 then 'P2 LL Pressure Alarm'
	end) as Alarm_Setpoint,
	
	(Select case
		when CHARINDEX('Go.KE', tag) = 1 then 'xxxxx'
		when CHARINDEX('Go.DI', tag) = 1 then 'xxxxx'
		when CHARINDEX('Go.DA', tag) = 1 then 'xxxxx'
		when CHARINDEX('Go.SI', tag) = 1 then 'xxxxx'
		when CHARINDEX('Go.EB', tag) = 1 then 'xxxxx'
		when CHARINDEX('Go.SJ', tag) = 1 then 'xxxxx'
		when CHARINDEX('Go.ST', tag) = 1 then 'xxxxx'
		when CHARINDEX('Go.SO', tag) = 1 then 'xxxxx'
		when CHARINDEX('GO.NV', tag) = 1 then 'xxxxx'
		when CHARINDEX('GO.SF', tag) = 1 then 'xxxxx'
		when CHARINDEX('Go.HU', tag) = 1 then 'xxxxx'
		when CHARINDEX('GO.SA', tag) = 1 then 'xxxxx'
		when CHARINDEX('GO.MI', tag) = 1 then 'xxxxx'
		when CHARINDEX('GO.PN', tag) = 1 then 'xxxxx'
		when CHARINDEX('GO.NB', tag) = 1 then 'xxxxx'
		when CHARINDEX('GO.FR', tag) = 1 then 'xxxxx'
		when CHARINDEX('GO.CC', tag) = 1 then 'xxxxx'
		when CHARINDEX('GO.YO', tag) = 1 then 'xxxxx'
	end) as Division,	
		
	(Select case 	
		when CHARINDEX('AVG',right(tag,3)) = 1 then 'Pressure Avg'
		when CHARINDEX('Lo',right(tag,2)) = 1 then 'Pressure Lo'	
		when CHARINDEX('Hi',right(tag,2)) = 1 then 'Pressure Hi'
		else '  '
	end) as Pressure_Trend,
	
	(Select case
		when CHARINDEX('GO.SF', tag) =1 then substring(substring(tag,4,9),1,2) + '_' +substring(substring(tag,4,9),3,2)+ '_' +
			substring(tag,8,4)
		when CHARINDEX('GO.FRSJ', tag) =1 then substring(substring(tag,4,9),1,2) + '_' +substring(substring(tag,4,9),3,2)+ '_' +
		substring(tag,8,4)
		when CHARINDEX('GO.SAFRFIER', tag) =1 then substring(substring(tag,4,10),1,2) + '_' +substring(substring(tag,4,9),3,3)+ '_' +
			substring(tag,8,6)	
		else substring(substring(tag,4,9),1,2) + '_' +substring(substring(tag,4,9),3,3)+ '_' +
			substring(tag,9,4)
	end)as SCADA_Location_Name



FROM xxxxxxxxxxxxxxxxxxxxxxxxx
where 


		( 
		Tag=xxxxxxxx

		)
	and time > DateAdd(M,-6,GetDate());
	
	
       		

Test
