/**
 *  Fibaro Wall Plug US child
 *
 *  Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except
 *  in compliance with the License. You may obtain a copy of the License at:
 *
 *	  http://www.apache.org/licenses/LICENSE-2.0
 *
 *  Unless required by applicable law or agreed to in writing, software distributed under the License is distributed
 *  on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License
 *  for the specific language governing permissions and limitations under the License.
 *
 */
metadata {
    definition (name: "Fibaro Wall Plug USB", namespace: "FibarGroup", author: "Fibar Group") {
        capability "Energy Meter"
        capability "Power Meter"
        capability "Configuration"
        capability "Health Check"

        command "reset"
        command "refresh"
    }

    tiles (scale: 2) {
        multiAttributeTile(name:"switch", type: "lighting", width: 3, height: 4, canChangeIcon: true){
            tileAttribute ("device.switch", key: "PRIMARY_CONTROL") {
                attributeState "on", label: 'USB', action: "", icon: "https://s3-eu-west-1.amazonaws.com/fibaro-smartthings/wallPlugUS/plugusb_on.png", backgroundColor: "#00a0dc"
            }
            tileAttribute("device.multiStatus", key:"SECONDARY_CONTROL") {
                attributeState("multiStatus", label:'${currentValue}')
            }
        }
        valueTile("power", "device.power", decoration: "flat", width: 2, height: 2) {
            state "power", label:'${currentValue}\nW', action:"refresh"
        }
        valueTile("energy", "device.energy", decoration: "flat", width: 2, height: 2) {
            state "energy", label:'${currentValue}\nkWh', action:"refresh"
        }
        valueTile("reset", "device.energy", decoration: "flat", width: 2, height: 2) {
            state "reset", label:'reset\nkWh', action:"reset"
        }
    }

    preferences {
        input ( name: "logging", title: "Logging", type: "boolean", required: false )
        input ( type: "paragraph", element: "paragraph", title: null, description: "This is a child device. If you're looking for parameters to set you'll find them in main component of this device." )
    }
}

def reset() {
    parent.childReset()
}

def refresh() {
    parent.childRefresh()
}
