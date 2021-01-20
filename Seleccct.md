

SELECT distinct vgo1.NV 
 FROM USEROBD.VGO vgo1 inner join USEROBD.VGR vgr1 on vgr1.NV = vgo1.NV AND vgr1.NPKLV = vgo1.NPKLV AND vgr1.NRS = vgo1.NRS AND vgr1.NPKLRV = vgo1.NPKLRV 
 where vgo1.MSGID>'2020-12-25-13.37.33.000000' and vgr1.ip is null
 and not exists 
 (SELECT * 
 FROM USEROBD.VGO vgo2 inner join USEROBD.VGR vgr2 on vgr2.NV = vgo2.NV AND vgr2.NPKLV = vgo2.NPKLV AND vgr2.NRS = vgo2.NRS AND vgr2.NPKLRV = vgo2.NPKLRV 
 where vgr2.nv=vgr1.nv 
 and vgo2.MSGID>vgo1.msgid and vgr2.ip is not null)


