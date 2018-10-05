Public Class Terbilang
{
	Public String TerbilangIndonesia(int nominal)
	{
		String strTot = String.Empty;
        String urai = String.Empty;
        String strJmlHuruf = String.Empty;
        String bil1 = String.Empty;
        String bil2 = String.Empty;
 		int y = 0;
		int x = 0;
		int z = 0;
 		strJmlHuruf = Convert.ToString(nominal);
 		urai = string.Empty;
		While (x < strJmlHuruf.Length)
		{
			x++;
			strTot = strJmlHuruf.Substring(x - 1, 1);
			y = y + Convert.ToInt32(strTot);
			z = strJmlHuruf.Length - x + 1;
			switch (Convert.ToInt32(strTot))
			{
				Case 1
    If ((z == 1 | z == 7 | z == 10 | z == 13))
					{
						bil1 = "SATU ";
					}
					ElseIf ((z == 4))
					{
						If ((x == 1))
						{
							bil1 = "SE";
						}
						Else
						{
							bil1 = "SATU ";
						}
					}
					ElseIf ((z == 2 | z == 5 | z == 8 | z == 11 | z == 14))
					{
						x = x + 1;
						strTot = strJmlHuruf.Substring(x - 1, 1);
						z = strJmlHuruf.Length - x + 1;
						bil2 = string.Empty;
						switch (Convert.ToInt32(strTot))
						{
							Case 0 : 
								bil1 = "SEPULUH ";
								break;
							Case 1 : 
								bil1 = "SEBELAS ";
								break;
							Case 2 : 
								bil1 = "DUA BELAS ";
								break;
							Case 3 : 
								bil1 = "TIGA BELAS ";
								break;
							Case 4 : 
								bil1 = "EMPAT BELAS ";
								break;
							Case 5 : 
								bil1 = "LIMA BELAS ";
								break;
							Case 6 : 
								bil1 = "ENAM BELAS ";
								break;
							Case 7 : 
								bil1 = "TUJUH BELAS ";
								break;
							Case 8 : 
								bil1 = "DELAPAN BELAS ";
								break;
							Case 9 : 
								bil1 = "SEMBILAN BELAS ";
								break;
						}
					}
					Else
					{
						bil1 = "SE";
					}
					break;
				Case 2 : 
					bil1 = "DUA ";
					break;
				Case 3 : 
					bil1 = "TIGA ";
					break;
				Case 4 : 
					bil1 = "EMPAT ";
					break;
				Case 5 : 
					bil1 = "LIMA ";
					break;
				Case 6 : 
					bil1 = "ENAM ";
					break;
				Case 7 : 
					bil1 = "TUJUH ";
					break;
				Case 8 : 
					bil1 = "DELAPAN ";
					break;
				Case 9 : 
					bil1 = "SEMBILAN ";
					break;
				Default: 
					bil1 = string.Empty;
					break;
			}
 			If ((Convert.ToInt32(strTot) > 0))
			{
				If ((z == 2 | z == 5 | z == 8 | z == 11 | z == 14))
				{
					bil2 = "PULUH ";
				}
				ElseIf ((z == 3 | z == 6 | z == 9 | z == 12 | z == 15))
				{
					bil2 = "RATUS ";
				}
				Else
				{
					bil2 = string.Empty;
				}
			}
			Else
			{
				bil2 = string.Empty;
			}
 			If ((y > 0))
			{
				switch (z)
				{
					Case 4 : 
						bil2 = bil2 + "RIBU ";
						y = 0;
						break;
					Case 7 : 
						bil2 = bil2 + "JUTA ";
						y = 0;
						break;
					Case 10 : 
						bil2 = bil2 + "MILYAR ";
						y = 0;
						break;
					Case 13 : 
						bil2 = bil2 + "TRILYUN ";
						y = 0;
						break;
				}
			}
			urai = urai + bil1 + bil2;
		}
 		Return urai + "RUPIAH";
	}
} 
