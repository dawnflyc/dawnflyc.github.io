参考 让反应堆电满了停，没电了开
local br = peripheral.wrap("back")
while true do
    local raio = br.battery().stored() / br.battery().capacity()
    local of = br.active()
    print("power", raio)
    if (raio < 0.2) then
        if (of == false) then
            br.setActive(true)
            print("open")
        end
    elseif (raio > 0.8) then
        if (of == true) then
            br.setActive(false)
            print("close")
        end
    end
    os.sleep(1)
end
