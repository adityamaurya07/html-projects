# html-projects
Club Mahindra Asonra Resort
import Image from "next/image"
// import Chart from "react-apexcharts"

import dynamic from 'next/dynamic'

const Chart = dynamic(() => import('react-apexcharts'), { ssr: false });

import { useState } from "react"
const Graph = () => {
    const [series,setSeries] = useState([
        {
            name:"Income",
            data:[10,25,37,75]
        },
        {
            name:"Expenses",
            data:[20,40,49,100]
        }
    ])
    const [options,setOptions] = useState({
        xaxis:{
            categories:[2011,2012,2013,2014,2015,2016,2017,2018]
        },
        yaxis: {
            title: {
              text: 'Value'
            },
          },
        legend:{
            position:"top",
            horizontalAlign:"right"
        },
        colors:["#FEC47A","#F86969"],
        chart:{
            toolbar:{
                show:false,
                tools:{
                    zoom:false
                }
            },
        },
        title:{
            text:"Earning Graph",
            style:{
                color:"#1E3A56",
                paddingTop:"12px"
            }
        }
    })
  return (
    <>
        <div className="container mt-4 flex gap-2">
            <div className="container h-[230px] bg-white pt-8">
                <div className="container flex flex-col justify-center items-center">
                    <Image src="/images/icon.png" width={50} height={50} alt="err" />
                    <h3 className="text-red-500 text-2xl">15<span className="text-sm pr-2">th</span>Years</h3>
                    <h5 className="text-sm font-bold">This Year Winner to Tomatus. <span className="text-red-500">Congratulation!</span> </h5>
                    <p className="text-[#B0CAD1] text-center text-xs p-2">A small river named Duden flows by their place and supplies it with the necessary regelialia. It is a paradisematic country.</p>
                </div>
            </div>
            <div className="container bg-white">
                <div className="mixed-chart">
                    <Chart
                        options={options}
                        series={series}
                        type="area"
                        height={"290px"}
                    />
                </div>
            </div>
        </div>
    </>
  )
}

export default Graph
