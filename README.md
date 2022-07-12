# bigdata-uamerica
using System;
using System.Data;

namespace CrtDataSet
{
    class Program
    {
        static void Main(string[] args)
        {
            //-- Instantiate the data set and table
            DataSet SongDS = new DataSet();
            DataTable songTable = SongDS.Tables.Add();

            //-- Add columns to the data table
            songTable.Columns.Add("ID", typeof(int));
            songTable.Columns.Add("Band", typeof(string));
            songTable.Columns.Add("Song", typeof(string));

            //-- Add rows to the data table
            songTable.Rows.Add(1, "Breaking Benjamin", "Diary of Jane");
            songTable.Rows.Add(2, "Three Days Grace", "Pain");
            songTable.Rows.Add(3, "Seether", "Fake It");
            songTable.Rows.Add(4, "Finger Eleven", "Paralyzer");
            songTable.Rows.Add(5, "Three Doors Down", "Citizen Soldier");

            //-- Cycle thru the data table printing the values to the screen
            foreach (DataTable table in SongDS.Tables)
            {
                foreach (DataRow row in table.Rows)
                {
                    Console.WriteLine(row["Band"] + " ~ " + row["Song"]);
                }
            }
        }
    }
